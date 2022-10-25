---
title: "The next big front for cloud competition: Location, location, location"
date: 2014-07-26
modified: 2014-07-26
draft: false
tags: ["Cloud"]
summary: "The leading public cloud providers are furiously standing up data 
centers around the world to grab market share country by country."
url: the-next-big-front-for-cloud-competition-location-location-location
---

_Originally_ [_written for
GigaOm_](https://gigaom.com/2014/07/26/the-next-big-front-for-cloud-competition-location-location-location/)_._

Now that we’re seeing intense competition in the cloud infrastructure market,
each of the vendors is looking for as many ways to differentiate itself as
possible. Big wallets are required to build the infrastructure and picking the
right locations to deploy that capital is becoming an important choice. Cloud
vendors can be innovative on a product or technical level, but location is just
as important — which geographies does your cloud vendor have data centers in and
why does that matter?

## Why is location important?

There are a number of reasons why a diverse range of locations is important:

- **Redundancy**: Compared to the chances of a server failure, whole data
  center outages are rare — but they can happen. In the case of [power
  outages](http://gigaom.com/2007/11/12/rackspace-outage-hits-home/), [software
  bugs](http://gigaom.com/2012/02/29/microsoft-azure-falls-down-goes-boom/) or [extreme
  weather](http://gigaom.com/2013/10/17/what-superstorm-sandy-taught-us-about-protecting-it-infrastructure/),
  it’s important to be able to distribute your workloads across multiple,
  independent facilities. This is not just to get redundancy across data
  centers but also across geographies so you can avoid local issues like bad
  weather or electrical faults. You need data centers close enough to minimize
  latency but far enough to be separated by geography.
- **Data protection:** Different types of data have different locality
  requirements, e.g. requiring personal data to remain within the EU.
- **User latency**: response times for the end user are very important in
  certain applications, so having data centers close to your users is
  important, and the ability to send traffic to different regions helps
  simplify this. CDNs can be used for some content but connectivity is often
  required to the source too.

Deploying data centers around the world isn’t cheap, and this is the area where
the big cloud providers have an advantage. It is not just a case of equipping
and staffing data centers — much of the innovation is coming from how efficient
those facilities are. Whether that means using the [local geography to make data
centers green](https://www.youtube.com/watch?v=VChOEvKicQQ), or [building your
own power
systems](http://gigaom.com/2013/11/15/how-amazon-is-building-substations-laying-fiber-and-generally-doing-everything-to-keep-cloud-costs-down/),
this all contributes to driving down prices, which can only truly be done at
scale.

## How do the top providers perform?

The different providers all have the concept of regions or data centers within a
specific geography. Usually, these are split into multiple regions so you can
get redundancy within the region, but this is not sufficient for true redundancy
because the whole region could fail, or there could be a local event like a
storm. Therefore, counting true geographies is important:

| Provider            | USA | Europe | Asia | Other |
| ------------------- | --- | ------ | ---- | ----- |
| Amazon Web Services | 3   | 1      | 3    | 1     |
| Microsoft Azure     | 5   | 2      | 4    | 1     |
| Google              | 1   | 1      | 1    | 0     |
| Rackspace           | 3   | 1      | 2    | 0     |
| Softlayer           | 5   | 2      | 2    | 0     |

Azure is in the lead with 12 regions, followed by Softlayer (9), Amazon (8) and
Rackspace (6). Google loses out, with only 3 regions.

## Where is the investment going?

It’s somewhat surprising that Amazon has gone for so long with only a single
region in Europe — although this may be about to change with [evidence of a new
region based in
Germany](http://www.nilsjuenemann.de/2014/07/new-aws-region-eu-central-in-germany.html).
If you want redundancy then you really need at least 2 data centers nearby,
otherwise latency will pose a problem. For example, replicating a production
database between data centers will experience higher latency if you have to send
data across the ocean (from the U.S. to Ireland, say). It’s much better to
replicate between Ireland and Germany!

Softlayer is also pushing into other regions with [the $1.2 billion investment
it announced for new data centers in
2014](http://blog.softlayer.com/2014/whats-next-1-2-billion-investment-15-new-data-centers).
Recently it launched Hong Kong and London data centers, with more planned in
North America (2), Europe (2), Brazil, UAE, India, China, Japan and Australia
(2).

The major disappointment is Google. It’s [spending a lot of money on
infrastructure](http://gigaom.com/2014/07/17/not-slowing-down-at-all-google-spent-2-67b-on-data-centers-in-q2/) and [actually
has many more data centers
worldwide](https://www.google.com/about/datacenters/inside/locations/index.html) than
are part of Google Cloud. Of course, Google is a fairly new entrant into the
cloud market and most of its demand is going to be from products like search and
Gmail, where consumer requirements will dominate. Given the speed at which
Google is launching new features, I expect this to change soon [if it’s really
serious](http://gigaom.com/2014/07/18/nobody-doubts-googles-cloud-intentions-anymore/) about
competing with the others.

## What about China?

I have specifically excluded China from the figures above, but it’s still an
interesting case. The problem is that while connectivity inside China is very
good (in some regions), crossing the border can add significant latency and
packet loss. Microsoft and Amazon both have regions within China, but they
require a separate account and you usually have to be based in China to apply.
Softlayer has announced a data center in Shanghai, so it will be interesting to
see whether it can connect their global private network with good throughput. As
for Google, it [publicly left China 4 years
ago](http://googleblog.blogspot.co.uk/2010/03/new-approach-to-china-update.html) so
it may never launch a region there.

It’s clear that location is going to be a competitive advantage, one where
Microsoft currently holds first place but will lose it to Softlayer soon. Given
the amount of money being invested, it will be interesting to see where cloud
availability expands to next.
