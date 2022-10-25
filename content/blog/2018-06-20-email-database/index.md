---
title: "Email is not a good database"
date: 2018-06-20
modified: 2018-06-20
draft: false
tags: ["Security"]
summary: "Email is insecure. Anything of any importance should be saved 
somewhere else. It's not a good database, so shouldn't be treated like one."
url: email-is-not-a-good-database
---

How far back does your email archive go? Years, decades? What kind of
discussions, opinions and sensitive files would a search reveal?

What damage could be done if someone got into your email? [Your thoughts on
people your
know?](https://en.wikipedia.org/wiki/United_States_diplomatic_cables_leak) [Maybe
crucial negotiation
documents?](https://en.wikipedia.org/wiki/Sony_Pictures_hack) Things that
probably shouldn’t be public?

Email is a terrible way to store information. It is not supposed to be a
database – it’s a method of communication. It’s a single place to find out
everything you have ever said to anyone.

Not only does email act like a repository of your own communications, documents
and discussions, every single from, to, cc and bcc has a copy. You might delete
something from your own inbox but it’s probably nicely replicated many times
around the world.

At Server Density, we had a policy of automatically deleting all email after 1
year. We had documentation retention policies for types of files which needed to
be kept and for how long e.g. financial records for 7 years. But they were all
retained in systems designed for the purpose, not email.

Anything of any importance should be saved somewhere else. Dedicated cloud file
storage allows you to control access, share links with expiry dates and manage
versions. You can encrypt sensitive files and audit access logs.

Knowing your legal obligations to retain specific data types and deleting
everything else is good practice. Combine this with sending expiring links to
files in cloud storage rather than attachments and you mitigate the risk
of [other people’s poor security hygiene
too](https://davidmytton.blog/cyber-security-leaving-the-door-unlocked/).

Email is insecure. It’s not a good database, so shouldn’t be treated like one.
