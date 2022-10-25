---
title: "A basic startup employee security checklist"
date: 2018-07-12
modified: 2018-07-12
draft: false
tags: ["Security", "Startups"]
summary: "There are lots of things you should be doing. At Server Density, we 
used a simple checklist that everyone would verify every 6 months. "
url: a-basic-startup-employee-security-checklist
---

Unless you’re just starting a new business from scratch, it is difficult to
force big security policy changes across everyone in the company.

There are lots of things you “should” be doing. Whether this is rolling out a
new device management platform to ensure everyone has the latest software
updates or moving everyone to use a single-sign-on platform for all company
logins, if you don’t do it from day one then it simply takes time to change
existing practices.

Various events might trigger a revamp of your approach to security. It might be
a big customer asking for supply chain assurances, it might be trying to sell
into a particular industry like finance of government, or it may even be a
security incident.

Security is never “done”. Rolling out device management across all company
computer equipment is a big, time consuming project. But there are small wins
that employees can do that will set the organisation apart from most other
businesses, because most companies are horribly insecure.

At Server Density, we used a simple checklist that everyone would verify every 6
months. Once the initial setup is done when an employee joins, it only takes a
couple of minutes to verify. It addresses the basics of [ensuring the doors are
locked](https://davidmytton.blog/cyber-security-leaving-the-door-unlocked/) and
doesn’t require any specialist knowledge for most steps. Here’s the checklist.

## A basic startup employee security checklist

This is specific to the services we used at Server Density, so may need
adjusting for your own environment.

1. Have you enabled 2 factor auth on key accounts?
   1. Braintree.
   2. Google.
   3. Github.
   4. [… All key company services listed here]
2. Do you have full disk encryption enabled?
3. Are you storing any sensitive or important files locally e.g. customer
   lists, strategy documents, private keys?
   1. If so, are they actually local or have they been placed into a cloud
      “dropbox” (e.g. Google Drive, Dropbox).
   2. If they are in a cloud dropbox, ensure they are either removed (and
      deleted from the cloud service) or encrypted (use PGP).
   3. If you subsequently encrypt a previously plain text file, be sure the
      cloud service has not just written a new version and you cannot restore
      the previous version!
4. Are you running the latest OS version?
5. Do you have a strong OS password?
6. Confirm the password activates on sleep / screensaver.
7. Are you running the latest browser version?
   1. Be sure to restart Chrome regularly so it can apply updates.
   2. [Enable
      click-to-play](https://krebsonsecurity.com/2013/03/help-keep-threats-at-bay-with-click-to-play/) to
      prevent browser plugin vulnerabilities.
8. Are you using a password manager e.g. 1Password?
   1. Do you have a strong master password?
   2. Is the master password different from your OS password?
   3. Are you using different passwords for every account?
9. Do you have a passcode on your mobile device?
10. [Review your Google Account
    security](https://security.google.com/settings/security/secureaccount) 1.
    If you set a backup email, make sure it also has multi factor authentication
    enabled. 2. Install [this Chrome
    Extension](https://chrome.google.com/webstore/detail/password-alert/noondiphcddnnabmjcihcjfbhfklnnep) to
    protect against phishing on your Google account.
