---
title: "Why don't data centers participate in demand response?"
date: 2023-02-13
modified: 2023-02-13
draft: false
tags: ["Data Center Energy", "Energy Systems", "Cloud"]
summary: "Data centers consuming too much energy at peak times - can't we just turn them off?"
canonicalUrl: https://www.devsustainability.com/p/why-dont-data-centers-demand-response
url: why-dont-data-centers-demand-response
---

Demand response is where a user of energy (usually electricity) varies its
demand for a period of time in response to a request from the grid operator.
This typically occurs when demand might outweigh supply. If it is not possible
to increase supply in response to higher prices, the next option is to ask some
users to reduce their demand. This is possible where that demand is not time
sensitive and can easily switch off for a time.

A common example of this is with air conditioning that could receive remote
instructions to temporarily set itself to a higher temperature. Another example
might be a fridge which could adjust its boundary of allowed ranges and not
switch on so frequently - a few extra degrees for a few hours probably makes no
difference.

In both of these scenarios, the consumer might be compensated through a variable
rate tariff. Price increases are a good way to reduce demand. Alternatively, a
bonus payment might be paid if demand is reduced during a specified time. This
can even work in reverse during periods of low demand where consumers can be
paid to take advantage of the abundant supply. [Octopus Energy in the
UK](https://octopus.energy/agile/) has several tariffs that incorporate this.

So why can’t this apply to data centers? Why do so few participate in demand
response programs?

Reliability.

![A photo of a data center at night in the dark](dark-data-center.png "Generated
by DALL-E 2 (“a large data center in the moonlit countryside, all in darkness,
no power, electricity pylons in the background”)")

The primary purpose of a data center is to provide a secure, reliable, and well
connected place for IT workloads to operate efficiently. Power is a crucial
aspect of this and data centers invest a lot of money into ensuring that the IT
equipment always has power. This involves backup batteries, generators, and
emergency fuel delivery contracts to ensure continuity.

If power to a data center could be taken offline at short notice it would either
need to shut down entirely or (more likely) would have to switch to an
alternative source of power. Shutting down entirely is impractical even if a
single entity controlled all the equipment and systems within the data centers.
Building applications to shift load is [very expensive and difficult to
do](/paper-notes-mitigating-curtailment-and-carbon-emissions-through-load-migration-between-data-centers/).
And switching to backup is a risky process in itself, even when tested
regularly. Long duration batteries are still too expensive and too immature in
their development to make them a reliable option, although large scale batteries
are
[being](https://blog.google/inside-google/infrastructure/cleaner-data-centers-batteries-included/)
[deployed](https://www.datacenterdynamics.com/en/news/google-picks-fluence-for-275mw-grid-supporting-battery-system-in-belgium/).

In theory the cloud makes load migration a lot easier. The concept of zones and
regions is well understood and APIs make it easy to create new resources.
Indeed, before Google Cloud was a proper product, Compute Engine zones [used to
turn
off](https://blogs.gartner.com/lydia_leong/2013/11/14/google-compute-engine-and-live-migration/)
for up to 2 weeks for maintenance!

Going a bit further up the stack to a larger geographical area, serverless
products might make this more feasible. If you deploy a Lambda function to “US
East”, but that means it’s distributed over several regions on the US East Coast
from Boston to Florida, that would cover a wide enough area to migrate a
workload in response to localized grid pricing. This could even be handled
transparently by the cloud provider themselves, routing based on carbon signals.
Google Cloud Storage already has this built into its [“Multi-Region” deployment
option](https://cloud.google.com/storage/docs/locations), although that is for
redundancy rather than reducing carbon.

However, the cloud does not make load migration cheap. Nothing about the cloud
is cheap - you’re buying managed services at all levels of the stack. Migration
of anything other than ephemeral loads immediately hits the problem of data
gravity and it becomes prohibitively expensive (and time consuming) to transfer
data out (or replicate it to multiple regions). Moving between zones is
insufficient because they are deliberately within a few tens of miles of each
other, which means they will be on the same electricity grid, with the same
pricing. Latency and replication delay becomes a problem as well.

The additional revenue of participating in demand response is therefore
meaningless in comparison to the risks and costs of migrating workloads. That’s
why data centers don’t (and won’t) participate in demand response.

There is an opportunity for cloud workloads, though. Edge services will make
this more likely - data can live centrally with compute migrating between edge
locations, caching appropriately. But it might be more expensive, especially
with networking fees. It remains to be seen how customers prioritize the
sustainability benefits of moving workloads spatially vs the costs of doing so.
