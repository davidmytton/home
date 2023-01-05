---
title: "Tool: Responder"
date: 2023-01-03
modified: 2023-01-04
draft: false
summary: "Attacking web applications."
---

{{< hacking-disclaimer >}}

<https://github.com/lgandx/Responder>

Auth responder/poisoner.

## Get

`git clone https://github.com/lgandx/Responder`

## Run

`sudo python3 Responder.py -I tun0`

or on Kali

`sudo responder -I tun0`

## SMB Requests

Check `/usr/share/responder/Responder.conf` has `SQL = On` and `SMB = On`
