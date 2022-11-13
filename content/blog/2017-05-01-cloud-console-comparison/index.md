---
title: "Why does the interface matter? Cloud provider consoles compared"
date: 2017-05-01
modified: 2017-05-01
draft: false
tags: ["Cloud"]
summary: "Developers are used to high quality design in consumer products, so 
they expect the same when using business products. Why is this important and 
how do the big 3 cloud providers compare?"
canonicalUrl: https://www.infoworld.com/article/3193339/why-does-the-interface-matter-cloud-provider-consoles-compared.html
url: why-does-the-interface-matter-cloud-provider-consoles-compared
---

_Originally_ [_written for
InfoWorld_](https://www.infoworld.com/article/3193339/why-does-the-interface-matter-cloud-provider-consoles-compared.html)_._

The big draw of cloud services is the fact that all resources are consumable via
APIs. Providing a consistent interface that developers can access is the first
step towards offloading the “undifferentiated heavy lifting” to a cloud
provider. Why build parts of your application infrastructure when you can make
use of a service built, maintained and continually updated by experts?

The challenges of providing a good API center around the design of the API
methods themselves, having good quality documentation, code samples and
libraries for major languages. What becomes more difficult is when you have to
complement the programmatic API with a web and/or mobile UI.

Every cloud provider offers a web based console which allows you to manage all
aspects of your cloud account. In the early days, this console could be very
simple -- just a few products, billing and user management was all that was
necessary. But as the number of products has expanded and the complexity of
those products has increased, having a single console to manage it all has
become a major area of focus.

## What are the challenges?

The main thing is product range. AWS has 18 top level categories of products,
ranging from Compute to Storage and from AI to Application Services. Each of
these has up to 15 products within them, not to mention the AWS Marketplace,
support and billing systems. This vast number of top level services all have sub
services and features, have interconnected components and all are in use to
different degrees by different customers. Google Cloud and Microsoft Azure have
similar challenges with the range of products they offer.

Providing a full set of infrastructure services is complex, and building an
interface to manage them has a number of things it must address:

- Discoverability. How do you categorize the products and ensure that
  customers know what they are called, especially with the prevalence of
  acronyms like ELB, GCE, CloudML, VPN and “code names” like StorSimple,
  HDInsight, Aurora and Firebase.
- Navigation. With potentially hundreds of different services and varying
  levels of hierarchy, a simple tab interface or range of icons is going to
  quickly break down. Search is going to be crucial, as is being able to
  quickly access recent services.
- Geographies. Different services have different regional availability,
  pricing and features. How do you make it clear which context you’re
  operating in and how does that work when services operate on a global,
  regional and zone level
- Consistency. With such complexity inherent in the product portfolio, having
  a consistent design language across the UI is important to reduce the
  overhead of actually using the interface itself. Different teams will likely
  be responsible for their own products, but having them all within a single
  console means you should not have different layouts, button styles, fonts,
  images, etc.

## How do the cloud providers stack up?

### AWS

The AWS console has had a very similar design since it was initially launched.
Minor design tweaks and the addition of search show gradual improvements but it
is still very basic in design. AWS is known for its complexity and the UI
doesn’t try to hide that.

You can switch between accounts and regions, although the currently selected
option doesn’t particularly stand out. There’s no real way to search resources
globally across the account, which can make it difficult to find what you might
be looking for, but you can pin services to the top bar to make them easy to
access.

The UI is very consistent, something which has improved over the years e.g.
billing and support moving away from the old Amazon.com style into AWS proper.

Amazon has a reputation for being efficient and frugal, words which you could
use to describe the AWS interface as well. It does the job with a minimalistic
design, which is probably perfect for a technical audience.

### Google Cloud Platform

The GCP console has changed radically several times over the past few years as
their cloud portfolio has expanded. GCP works on the basis of projects, which
were originally entirely self contained but recently gained the ability to be
linked under custom organisational and billing hierarchies. GCP also doesn’t use
geographies in the same way as AWS. Instead, specific resources have zone or
regional properties but everything is managed together so that you have a global
view of the infrastructure. This makes it easier to get a top down view of all
environments but is quite different if you’re used to them being logically
separate like on AWS.

As you might expect from Google, search is presented as a central part of the
web console. It is not limited just to products -- you can search many of your
resources as well e.g. for compute instance names, even across projects.

The design language is becoming consistent across Google products but completing
this is clearly a big project! Even within GCP, you can still see older products
like BigQuery using different UI designs, or acquired products like Stack Driver
not really fitting in properly. The support ticket interface is also poorly
implemented compared to the main GCP console. Rearchitecting and merging legacy
components is difficult, even for Google!

From a design perspective, the GCP console is very nice to use and builds in a
lot of functionality for ease of use e.g. menu pinning as well as for power
users e.g. keyboard shortcuts and search. Google are iterating quickly to make
improvements but there’s still some work to do with older areas of the platform.

### Microsoft Azure

The new Azure portal is a major improvement on the old portal, but for me
continues to be one of the worst interfaces I’ve had to use. Even the login
authentication is confusing with the many different login screens and URLs that
Microsoft seems to adopt for its online services.

Whilst the Azure portal design style is consistent across many of the other
Microsoft services, the model of navigating horizontally through a product
hierarchy is poorly implemented, buggy and really breaks down when trying to use
a small screen on a laptop or tablet. You can see the similarities between the
Azure interface and Windows itself, which probably means that Windows users will
be more comfortable and familiar with how it works.

With so many products and options, it is very difficult to find what you’re
looking for, especially when the text labels disappear and are replaced with a
tiny icon that you must memorise! At least the older UI has been retired now,
because I remember that billing was still in the older interface until recently,
which made figuring out how to perform simple actions like downloading an
invoice very confusing.

## Why does the interface matter?

With more and more resources being deployed to the cloud, being able to manage
them is already a critical part of many businesses.

Cloud providers risk losing a competitive bid because their products are too
complex to use. Unlike in the old world of enterprise software, the end user is
now more often than not the buyer and decision maker. Developers will pick the
provider with the best management interface, which includes the web UI as well
as the API. With design a central part of consumer products, it’s not
unreasonable to expect good quality design as part of business products too.

As an example of this, I was recently making a payroll tax payment through the
Silicon Valley Bank online banking interface. Their UI is the worst I have ever
used -- it is confusing, has totally different designs depending on which
section you are in and has poorly implemented workflows which drop you into
different views repeatedly and unnecessarily. This resulted in a payment not
being made on time and interest charges being levied, all because the UI wasn’t
clear about the status of a payment pending approval. Banking is the ultimate
legacy industry and it shows the opportunity for challenger banks. I am an
investor in the UK consumer banking startup, Monzo, and the contrast in user
experience is stark.

When critical resources are being managed through a third party interface, you
want to ensure that interface provides accurate information that is easy to
understand, with design that make it easy to manage and avoid mistakes. This is
a principle that we take seriously at my company, Server Density, when
presenting critical monitoring data through alerts and graphing. You don’t want
to be bogged down in trying to navigate a poorly designed UI in an emergency.
Making a mistake with online banking has financial consequences just as much as
making a mistake with a cloud provider interface could result in downtime,
deleted data and loss of revenue.

The interface matters.
