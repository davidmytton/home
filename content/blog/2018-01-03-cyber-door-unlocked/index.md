---
title: "Cyber security and leaving the door unlocked"
date: 2018-01-03
modified: 2019-08-08
draft: false
tags: ["Security"]
summary: "When it comes to insurance, it’s the same as locking up and 
installing an alarm"
url: cyber-security-leaving-the-door-unlocked
---

A standard part of home or office contents insurance is making sure you use a
lock from a list of approved manufacturers, and then ensure that the lock is
actually engaged when you’re absent. Enabling other security mechanisms such as
alarms is also typically required.

This seems entirely reasonable and simple common sense: if you leave a building
unlocked and your belongings are stolen, it’s your own fault – you were
negligent.

It’s not quite the same when it comes to cyber theft.

Even though you can purchase insurance to cover you against the risks of cyber
attack, hacking, ransomware and data loss, the policies are much vaguer when it
comes to understanding your responsibilities.

In a physical contents policy, it is sufficient to use the term “locked” to
describe the state the building must be in to be considered sufficiently
protected. When applying for the policy you will be asked if there is an alarm
and in theory the presence of one should reduce the premium. The same isn’t the
case when applying for a cyber insurance policy. I think it should be.

## Basic security steps

There are two steps you must take to secure your online accounts:

1. Use a password manager, with unique passwords for every online account that
   are [at least 12 characters in
   length](https://blog.codinghorror.com/your-password-is-too-damn-short/) (as
   of Jan 2018, this will change over time).
2. Use 2 factor authentication using a TOTP app such as Google Authenticator,
   not SMS. Or [even
   better](https://www.yubico.com/2016/02/use-of-fido-u2f-security-keys-focus-of-2-year-google-study/),
   use [a security
   key](https://techsolidarity.org/resources/security_key_gmail.htm).

Having the same password (or a small number of passwords) for your online
accounts is the single biggest reason why account compromise is so frequent. A
single breach of any online service will reveal your password for everything
else, something which happens on a regular basis.

Without a password manager, this becomes difficult to achieve, especially since
you will want to use a random selection of numbers, letters and special
characters. The main reason to use a passphrase with combinations of words is to
make it easier to remember. Using a password manager means you don’t even have
to remember anything except the single master password, can protect against
phishing because auto-fill matches are based on URL patterns and you can quickly
enter credentials with keyboard shortcuts.

You have to expect that your password will be leaked (or possibly guessed given
sufficient compute power), and so that is why having 2 factor authentication is
so important. This is a great example of having layers of security so a breach
of one type of protection is mitigated by another.

If you don’t use both of these “techniques” for at least your email and ideally
for every account, you are negligent. It’s the same thing as leaving your
property unlocked.

## Applying this to cyber policy insurance

Just implementing these security measures significantly improves your security
and should really be a standard part of applying for cyber insurance just like
asking about alarm systems is for contents insurance. Not using either should
therefore increase your premium.

But given the number of people who are still acting negligently with regards
their own cyber security, perhaps it’s not yet been considered in the risk
analysis for insurers. Maybe so many people don’t bother with proper security
that it doesn’t show up in their premium modeling yet.

Or maybe it does. If you look closely at the insurance wording, you might find
something like this:

> What is not covered – pre-existing problems: anything likely to lead to claim,
> loss, breach, privacy investigation, illegal threat or interruption which you
> knew or ought reasonably to have known about before we agree to insure you.
>
> <cite>Source: [Hiscox Cyber
> Policy](https://www.hiscox.co.uk/sites/uk/files/documents/2017-03/13388-cyber-and-data-policy-wording.pdf)</cite>

This is vague enough to give the insurer scope to exclude many claims for poor
security practices – “ought reasonably to have known about” easily covers not
using the two security techniques above. There is enough advice online and from
official government channels saying the same thing
([2FA](https://www.ncsc.gov.uk/guidance/using-passwords-protect-your-data) and [password
managers](https://www.ncsc.gov.uk/blog-post/what-does-ncsc-think-password-managers))
for this now to be considered reasonable knowledge.
