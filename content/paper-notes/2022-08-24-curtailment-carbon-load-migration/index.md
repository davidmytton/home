---
title: "Paper notes – Mitigating Curtailment and Carbon Emissions through Load Migration between Data Centers"
date: 2022-08-24
modified: 2022-08-24
draft: false
tags: ["Paper Notes", "IT Energy", "Data Center Energy"]
summary: "This is a good paper that makes valid points about the possibilities 
of migrating flexible IT workloads, however it makes classic assumptions I see 
in most papers that discuss this topic."
url: paper-notes-mitigating-curtailment-and-carbon-emissions-through-load-migration-between-data-centers
---

## Paper

Zheng, J., Chien, A.A., and Suh, S. (10/2020). Mitigating Curtailment and Carbon
Emissions through Load Migration between Data Centers. Joule *4*,
2208–2222. <https://dx.doi.org/10.1016/j.joule.2020.08.001>

## Notes

- Curtailment and long-distance transmission of renewable energy[^catch] is a
  major challenge for the transition of the energy system to 100% clean energy.
  It’s one of the details that many environmentalists forget (or don’t know
  about) when advocating for rapid decarbonization of the energy system
  particularly if they only focus on solar and wind. That, and the challenges of
  variability and energy storage.
- I try and catch myself whenever I say “renewables” because instead we should
  be talking about “clean energy” i.e. wind, solar, hydro, and nuclear, with gas
  as a transition fuel.
- Researching strategies for dealing with these challenges is therefore an
  important area of work. Understanding how the grid is used and making that
  smarter is going to be an important lever for managing future energy systems.
- Demand response often comes up in the context of data centers and IT workloads
  because unlike other large energy users – typically heavy industry – IT
  workloads have a high degree of temporal and spatial flexibility. At least
  theoretically.
- This paper shows that moving workloads between data centers between different
  regions in the US could enable significant carbon reduction and absorb energy
  that would otherwise have been curtailed.
- This is particularly relevant because the paper cites an interesting statistic
  about the density of data center capacity within small regions of the US: “In
  the second half of 2018, North Virginia absorbed over a third of the world’s
  new data center capacity, with an addition of 270 megawatts (MW) of data
  center power”
  ([source](https://www.datacenterknowledge.com/cloud/cloud-data-center-construction-boom-two-charts)).

[^catch]:
    I try and catch myself whenever I say “renewables” because instead we
    should be talking about “clean energy” i.e. wind, solar, hydro, and nuclear,
    with gas as a transition fuel.

However, the paper makes several major assumptions which I see in almost every
academic paper on data center demand response or carbon related workload
migration:

**Assumption:** Data centers are underutilized and provisioned for peak
capacity, which is a waste. That capacity could be used for workloads migrated
from other regions.

**Comment:** Traditional data centers are notoriously underutilized. In the days
of buying hardware for colo it was necessary to overprovision for peak capacity
because of the lead times for deploying new equipment. The move to cloud
computing means this is less of a problem for the customer because of the
flexibility of cloud services, and for the cloud provider because they can
allocate resources more efficiently.

However, redundancy and reliability is a major reason for deploying additional
capacity. Data centers should be efficient, but they must be reliable. Being
able to fail over when there is a system failure is part of the architecture of
well designed applications. This is why you typically see systems utilized to no
more than 50% of capacity because you need to be able to switch to the idle
infrastructure in an outage.

Pushing past 50% is possible, and the big cloud providers anecdotally say they
do this, but running your system at 100% is only sensible if you don’t require
redundancy.

**Assumption:** Workloads are flexible and can be distributed geographically.

**Comment:** Distributed computing is hard! There’s a reason why most
applications deployed to the cloud are only redundant across zones – adding even
a small amount of latency introduces difficult computer science problems like
storage consistency and database leadership coordination. Multi-zone is
generally sufficient (and highly recommended) for most applications.
Distributing static assets is straightforward, which is why CDNs are trivial for
developers to use (although cache purging is still tricky). As soon as you need
to sync state across geographies then it gets more difficult.

In the cloud there is often the assumption that all regions are equally capable,
but that is not true. For example, AWS treats each region as (almost) entirely
independent from any other. New products capabilities are rolled out to
different regions at different times and of course there are pricing differences
between regions as well.

Some geographic regions are too small to move between! The paper uses the US as
an example, but the US is unusual in terms of its large geographic size yet it
is generally considered a “single market” from a legal perspective. That’s not
true in Europe where different countries have different data protection laws.
AWS has a single region in Germany, for example, so it may not be legally
possible to migrate workloads to France or the UK to take advantage of lower
carbon intensities.

Lots of innovation is happening in the distributed computing space. Products
like Cloudflare’s [durable
objects](https://developers.cloudflare.com/workers/learning/using-durable-objects/), [R2](https://developers.cloudflare.com/r2/) (object
storage) and [D1](https://blog.cloudflare.com/introducing-d1/) (edge SQL
database), and [Google Cloud Spanner](https://cloud.google.com/spanner) are
trying to solve these issues.

**Assumption:** Delay-tolerant workloads like big data analysis, image
processing and scientific computation are good candidates for migration.

**Comment:** The main problem with migrating these workloads is the cost of
moving the data. All the cloud providers charge for internal network transfer,
which is usually cheaper between zones but expensive between regions. These
workloads are the kind that operate on huge volumes of data, which would likely
make it prohibitively expensive to move. It would also take a long time.

This means that the workloads that are more fault tolerant and can be operated
at higher utilization are also the workloads that are more difficult to move
because of the cost and network transfer times.

**Assumption:** There are “advanced algorithms and automation mechanisms in
place to enable the load migration”.

**Comment:** Outside of the managed database products like Google Cloud Spanner,
I’ve yet to see any evidence of these types of automated mechanisms. Migration
within zones, such as the ability to migrate VMs for maintenance, is already
possible, so perhaps this is a case of extending those capabilities across
regions – but then you start to encounter the same issues of latency, data
transfer cost, and consistency.

[Spot instances](https://aws.amazon.com/ec2/spot/) which price capacity based on
market signals are a good example of introducing incentives to run tasks in
particular locations at more optimal times, but they don’t do anything for the
migration itself.

As noted above, there is a lot of innovation happening in distributed computing,
so I expect this to get better and improve over time.

## Conclusions

This is a good paper that makes valid points about the possibilities of
migrating flexible IT workloads, however it makes classic assumptions I see in
most papers that discuss this topic. The big assumptions are that the data
centers are fungible entities where the operator has complete control, the goal
is to optimize for efficiency, and it is trivial to move huge volumes of data
cheaply.

We are starting to see this with the big tech companies who own many data
centers. Google is an example used in the paper, but it’s telling that it is the
only example. [Google is only doing it for a small number of
workloads](https://blog.google/inside-google/infrastructure/data-centers-work-harder-sun-shines-wind-blows/).
That shows how difficult it is.

This paper is good inspiration for future research direction. I think we’ve seen
enough evidence of the benefits of such capabilities that time and effort should
be directed towards building the technologies needed to achieve these
migrations. And if the cloud providers [could reduce their data transfer
fees](https://blog.cloudflare.com/aws-egregious-egress/), that would be nice as
well.
