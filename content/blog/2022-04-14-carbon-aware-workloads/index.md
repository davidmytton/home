---
title: "Carbon aware workloads – current status, limitations, and opportunities"
date: 2022-04-14
modified: 2022-04-14
draft: false
tags: ["Cloud", "IT Energy", "Carbon Awareness"]
summary: "Why isn’t carbon aware workload scheduling more common? Data center 
level scheduling is infeasible, so what are the opportunities for developers to 
implement more granular functionality?"
url: carbon-aware-workloads-current-status-limitations-and-opportunities
---

Moving compute workloads to regions with lower-carbon electricity is one way to
reduce the impact of their associated data center energy consumption. The
problem is that carbon intensity changes throughout the day as the grid fuel mix
changes.

As a result, I’ve seen lots of papers proposing algorithms for carbon aware
scheduling. They typically involve analyzing grid emissions data for each data
center region and then migrate workloads to regions with lower carbon intensity.
This can be achieved using emissions data APIs from [organizations like
WattTime](https://www.watttime.org/api-documentation/#introduction),
particularly for forecasting near-future emissions so that migrations can occur
in-advance of immediate need.

A number of problems stand out from my initial research:

1. **Data**. Reliable and consistent data is crucial for these systems to work.
   However, there are a large number of grid operators, even within countries,
   which means a large number of data sources. These don’t always match with the
   region a data center is in, may not provide forecasted carbon emissions, and
   may be private. This is why organizations
   like [WattTime](https://www.watttime.org/) and [ElectricityMap](https://electricitymap.org/) have
   developed commercial API products.
2. **Workloads are different.** Data center level scheduling and migration is
   not realistic for most environments. [Google has blogged about how it
   migrates some
   workloads](https://blog.google/outreach-initiatives/sustainability/carbon-aware-computing-location/),
   such as YouTube video encoding, based on carbon intensity, but few
   organizations have complete control over the entire technology stack from
   software through to data center energy contracts. Most of the papers I’ve
   read focus too much on whole data centers rather than more granular
   workloads. They assume IT users can just move everything from one data center
   to another, which isn’t really feasible.
3. **Multiple IT considerations.** Carbon intensity is just one of many factors
   infrastructure teams need to think about. Latency, availability of cloud
   services (cloud regions are not equal, even from the same vendor), and data
   protection are just a few reasons why you might pick one cloud region over
   another.

These reasons may be why we’ve seen limited uptake of carbon aware scheduling.
They are often too high-level or think that reducing carbon intensity is the
only priority. SDKs need to be written to make it easy for developers and
infrastructure operators to implement at a granular level where it makes sense
in their applications.

An example of one such approach is [a low carbon Kubernetes scheduler described
in a 2019 paper by James &
Schien](http://ceur-ws.org/Vol-2382/ICT4S2019_paper_28.pdf). This describes an
approach where the Kubernetes scheduler is adapted to prioritize new node
placement based on carbon intensity data from solar energy (and could be
extended to cover other renewable energy sources). Unfortunately, I could not
find the actual code, and it still assumes that the cluster can be re-deployed
in a new, low-carbon zone and the old cluster is deleted. This would be fine for
stateless workloads, but isn’t suitable for those using persistent data where
large volumes need to be migrated (or replicated).

I’m spending more time looking into what more can be done here. For example:

- Can a carbon aware load balancer route requests to lower-carbon backends?
  Would this incur bandwidth overhead that mitigates the benefits?
- Can low-carbon be indicated as a preference in cloud environments? The
  platform operator is going to have the best data from energy contracts and
  location-specific grid mix data. For example, the [Green Compute option for
  Cloudflare Workers](https://blog.cloudflare.com/announcing-green-compute/).
- Can job queues consider carbon intensity when they route tasks to workers?
  This depends on whether the job needs to be executed immediately or can handle
  some delay.
- What can user devices do to help the user reduce energy consumption at times
  of higher carbon intensity. For example, [the new update scheduling
  functionality in
  Windows](https://arstechnica.com/gadgets/2022/03/microsoft-is-trying-to-lower-carbon-emissions-via-windows-update-of-all-things/).

Software developers play an important role in improving the energy impact of the
products they work on because they have more impact than behavior change from
individuals. Microsoft changing when Windows runs its update processes will
impact billions of users. Encoding video at less carbon-intensive times of day
will impact the many thousands of hours of video. Making it easier for
developers to build this functionality seems like an interesting place to focus.
