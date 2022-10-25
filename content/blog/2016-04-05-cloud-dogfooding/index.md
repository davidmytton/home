---
title: "The importance of 'dogfooding' in the cloud"
date: 2016-04-05
modified: 2016-04-05
draft: false
tags: ["Cloud"]
url: the-importance-of-dogfooding-in-the-cloud
---

_Originally_ [_written for
InfoWorld_](https://www.infoworld.com/article/3051017/the-importance-of-dogfooding-in-the-cloud.html)_._

The term "dogfooding" is used to describe companies using their own products.
The idea is that by being a user, the company will find issues with products and
improve their overall experience.

Many software products are created out of their founders' need for a better
solution than already exists. They will have already used the competition and
researched the alternatives, so when they build something new it's to satisfy
their own needs. If you don't like your current CRM and you build an
alternative, you're going to use your own CRM product to sell it to customers.

## Degrees of dogfooding

At some companies, the products are created from internal technology and then a
separate, productized version is sold to customers. The underlying technology is
the same, but the implementation and deployment are different. You might write a
paper on a new approach to systems management, then a third party might
implement that paper with an open source project.

With others, the product might be intended for a completely different target
audience and never used internally. You might be a massive corporation and one
of your products is small business accounting, but you use an enterprise-grade
ERP solution to run your business.

The problem is, the further away a company gets from its customers, the more it
loses out on the dogfooding effects. It might miss bugs or release sub-optimal
workflows. A product platform might be suffering an outage, but if the company's
core business doesn't run on it there is less of an incentive to fix problems as
its own operations aren't affected. This is especially the case if the product
only makes up a tiny part of the company's revenue.

## Why is this important for the cloud?

The whole point of the cloud is that the services and infrastructure are run and
managed by an expert third party. You trust them to keep the system running,
optimize performance, and continually fix issues.

This is important for SaaS but even more important for IaaS because companies
rely on IaaS services -- such as compute, databases, networking, and storage --
as critical parts of their infrastructure. One argument for running your own
private infrastructure is that at least you have control and own the incentive
to ensure it works!

The top three cloud providers -- AWS, Azure, and Google Cloud -- have spun out
of companies that have very different core revenue generators. Even now, Amazon,
Microsoft, and Google still derive the majority of their revenue from other
sources. The contribution from cloud is increasing, but this fact makes
dogfooding particularly important for customers' trust and security.

## How do the cloud providers stack up?

AWS is the leader in the space and announced that [as of late 2010, Amazon.com
was running 100% on AWS](https://www.youtube.com/watch?v=dxk8b9rSKOo&t=7m25s).
It also runs many of its other products, [such as
Alexa](http://aws.amazon.com/solutions/case-studies/alexa/), through AWS and
it's clear that AWS is a core part of how Amazon runs its [entire
business](https://www.youtube.com/watch?v=kawZBGCLBJU).

Microsoft is [also making use of Azure for its key
products](http://www.channelregister.co.uk/2013/12/16/scott_guthrie_azure/).
Office 365 uses the Azure Directory Service and Xbox Live runs off Azure. Skype
is also running its backend on Azure. This has been proven from past Azure
outages that also affected key Microsoft services!

Google seems different. It makes many statements that when you're using Google
Cloud Platform you're building on top of Google's infrastructure. This is
technically correct because you are using Google's data centers and networking.
However, no Google products actually run on Google Cloud Platform.

The underlying technology is similar (or the same), but what you are buying when
you purchase cloud services from Google Cloud is productized, separated versions
of the technologies Google uses internally. While Amazon.com runs on AWS EC2,
Google Search is not running off Compute Engine.

This is a key difference, as recent outages have shown. You know that when Azure
has a problem and it takes Skype and Xbox live offline, that has a major impact
on different Microsoft business units. The same can be said of AWS outages
affecting Amazon.com -- there's a big incentive to fix the problem! However,
when Google had [its recent 12-hour outage that took Snapchat
offline](http://www.theregister.co.uk/2015/12/09/snapchat_titsup_on_heels_of_google_app_engine_outage/),
it didn't impact any of Google's real revenue-generating services. Google Cloud
Platform likely produces an insignificant amount of revenue compared to Adwords.
What would the impact have been if Google Search was down for 12 hours?

Google is undoubtably serious about being a player in the cloud. It has the
right people working on the right things, but it's still missing the right
incentives from a business perspective.

Alongside impressive [customer
announcements](https://cloudplatform.googleblog.com/2016/03/how-Google-is-bringing-cloud-computing-innovation-to-the-enterprise.html) from
the likes of Best Buy and Spotify, Google should be figuring out how to move all
of its own products to run on top of Google Cloud Platform. That is the only way
it is going to improve its reliability and understand how to build a product for
massive scale at an enterprise level. Google needs to dogfood its own cloud.
