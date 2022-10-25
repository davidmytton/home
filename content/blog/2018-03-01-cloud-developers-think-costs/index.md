---
title: "How the cloud changes how developers should think about costs"
date: 2018-03-01
modified: 2018-03-01
draft: false
tags: ["Startups", "Cloud"]
summary: "From fixed pricing per month to billing per function call, the cloud 
changes how developers should think about their application development."
url: how-the-cloud-changes-how-developers-should-think-about-costs
---

In the beginning there were servers, and they had a fixed cost per month. You
ordered a certain spec and had a fixed price which was predictable every month.
Sometimes you might exceed your bandwidth allowance but most hosting companies
included a huge allowance so that was unlikely.

Regardless of how little or how much traffic served and activity performed, the
cost remained the same.

For many early switchers to the cloud, the cost remained somewhat fixed.
Although you didn't contract a known price up front (before instance
reservations), if you were just using VMs (probably on EC2) then you were still
paying a fixed fee.

Network usage was the first real "pay as you go" element for most people moving
to the cloud. Both public and private traffic was billed for precisely the
amount used, which might have been a nice reduction but was probably a nasty
surprise.

Moving from fixed, all inclusive contracts to pay as you go removes a safety net
which makes you responsible for optimising your network usage whether it is
wanted or not. You no longer have control over spikes and have to pay for sudden
popularity or malicious attacks.

This is quite a drastic change of mindset, particularly with regards internal
traffic. Verbose network protocols such as for database replication or queuing
systems suddenly have a real impact on your budgeting, yet they are very
difficult to predict because they're out of your control.

But that's just the beginning.

For new cloud-first architectures, every single element of your architecture is
billed on a usage basis. Every message in a queue. Every row in a database.
Every serverless function call. You can just as easily save a lot of money on
low traffic applications as blow through your budget with highly trafficked
systems, poor design or bugs.

For developers, this means efficiency matters again. Performance improvements
have a direct impact on the bottom line and developer time spend on optimising
and refactoring can now be given a dollar value.

The gain is in handing the undifferentiated heavy lifting to a cloud service.
Instead of spending time reinventing a standardized component, time can now be
spent on the core application code that differentiates you service.

DevOps no longer really means developers understanding how to operate their
applications. It's more about how their applications operate in terms of
performance, and therefore cost.

This is quite a shift in mindset.
