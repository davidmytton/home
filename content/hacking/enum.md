---
title: "Enumeration Checklist"
date: 2023-01-03
modified: 2023-01-04
draft: false
summary: "Checklist for enumerating a box."
---

{{< hacking-disclaimer >}}

## Setup

`export IP=http://10.10.10.10`

## nmap

```bash
sudo nmap -p- $IP --open # Just show open ports
sudo nmap -p- -Pn -sS -n -sC -A -T4 -v $IP # david exploit scan
sudo nmap -v -sV -sC -O -T4 -n -Pn -oA fastscan $IP # 1000 port fastscan
sudo nmap -v -sV -sC -O -T4 -n -Pn -p- -oA --min-rate 5000 fullfastscan $IP # all port fastscan
```

Also try `-sU` for UDP.

- **Extras**
  - [Threader3000](https://github.com/dievus/threader3000)
  - **Port scan (basic):** `nmap -sV IP`
  - **Port scan (advanced):** `nmap -sS -sV -sC -O -T4 -Pn -n IP`
  - **Network sweep:** `nmap -sn 192.168.0.1-254`
  - **Enumerate Samba:** `nmap -p 445 --script=smb-enum-shares.nse,smb-enum-users.nse IP`
  - **Enumerate network fs:** `nmap -p 111 --script=nfs-ls,nfs-statfs,nfs-showmount`
  - **Scan for vulns:** `nmap -sV -vv --script vuln IP`
- **Opts**
  - `-p-` all ports
  - `-Pn` assume online
  - `-sS` TCP SYN
  - `-n` don’t do host resolution
  - `-sC` exploit script scan
  - `-A` OS detection
  - `-T4` timing template 4
  - `-v` verbosity
- **No nmap**

  ```bash
  for PORT in {0..1000}; do timeout 1 bash -c "</dev/tcp/172.19.0.1/$PORT &>/dev/null" 2>/dev/null && echo "port $PORT is open"; done
  ```

- Can also try [RustScan](https://github.com/RustScan/RustScan).

## Fuzzing

### Directories

```bash
ffuf -c -w /usr/share/seclists/Discovery/Web-Content/raft-large-directories.txt:FUZZ -u http://$IP/FUZZ -t 200 -fc 404
```

```bash
ffuf -c -w /usr/share/seclists/Discovery/Web-Content/raft-large-directories.txt:FUZZ -u http://$IP/FUZZ/ -t 200 -fc 404
```

### Extensions

```bash
ffuf -c -w /usr/share/seclists/Discovery/Web-Content/raft-large-extensions.txt:FUZZ -u http://$IP/blog/indexFUZZ -t 200 -fc 404
```

### Files

```bash
ffuf -c -w /usr/share/seclists/Discovery/Web-Content/raft-large-files.txt:FUZZ -u http://$IP/blog/FUZZ.php -t 200 -fc 404
```

### Subdomains (vhost)

```bash
gobuster vhost -u https://example.htb -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -k
```

```bash
ffuf -c -w ~/Sync/Sec/wordlists/SecLists/Discovery/DNS/subdomains-top1million-5000.txt:FUZZ -u http://trick.htb -H "Host: preprod-FUZZ.trick.htb" -t 200 -fs 5480
```

## Web - SQL Injection?

Copy as cURL into `sqlmap`.

## Other services

- [Enum DNS](https://book.hacktricks.xyz/network-services-pentesting/pentesting-dns)

  - Commands to try:

    ```python

        dnsrecon -r 127.0.0.0/24 -n {IP} -d {Domain_Name}
        dnsrecon -r 127.0.1.0/24 -n {IP} -d {Domain_Name}
        dnsrecon -r {Network}{CIDR} -n {IP} -d {Domain_Name}
        dig axfr @{IP}
        dig axfr {Domain_Name} @{IP}
        nslookup
            SERVER {IP}
            127.0.0.1
            {IP}
            Domain_Name
            exit
    ```

- [Enum SMTP](https://book.hacktricks.xyz/network-services-pentesting/pentesting-smtp)

## LFI

`/index.php?page=..././..././..././..././..././etc/passwd`

## SSTI

### General tests

```python
{{7*7}}
${7*7}
<%= 7*7 %>
${{7*7}}
*{7*7}
#{7*7}
```

### Other payloads

[https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Server Side Template Injection/README.md](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Server%20Side%20Template%20Injection/README.md)
