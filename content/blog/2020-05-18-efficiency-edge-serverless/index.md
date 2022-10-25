---
title: "Energy efficiency, edge compute and serverless"
date: 2020-05-18
modified: 2020-09-18
draft: false
tags: ["Data Center Energy", "Serverless", "Energy Efficiency", "Programming"]
summary: "We want to encourage more efficient use of cloud resources but 
designing incentives is hard. That changes with serverless and edge compute. 
Now energy usage is linked to price."
url: energy-efficiency-edge-compute-and-serverless
---

Over the last 10 years, data centre energy consumption has only grown by 6%
despite a massive increase in usage: x6 more compute instances, x10 more network
traffic and x25 more storage capacity in 2018 compared to 2010 ([Masanet et al,
2020](https://doi.org/10.1126/science.aba3758)). This is the result of [major
improvements in the energy
efficiency](https://davidmytton.blog/data-center-energy-and-the-importance-of-efficiency/) of
servers, storage and data centre facilities.

![Historical energy usage and projected energy usage under doubled computing
demand](historical-data-center-energy.png "Historical energy usage and projected
energy usage under doubled computing demand ([Masanet et al,
2020](https://doi.org/10.1126/science.aba3758)).")

The decoupling of energy from usage has been helped by a move to the cloud. 53%
of servers are expected to be in hyperscale facilities by 2021 ([Cisco,
2018](https://www.cisco.com/c/en/us/solutions/collateral/service-provider/global-cloud-index-gci/white-paper-c11-738085.html))
and the cloud computing market has grown from $6bn in 2008 to $288bn in 2019
([Forrester,
2019](https://www.tatacommunications.com/wp-content/uploads/2019/02/Forrester-Report.pdf)).

Moving to the cloud is a positive for energy efficiency because the big cloud
providers – Amazon, Google and Microsoft – have huge budgets dedicated to R&D.
Small percentage improvements in their overall energy efficiency translate into
large dollar amounts, but also mean that customers benefit from those
improvements automatically.

For example, Google’s electricity usage over the last 6 years has increased by
172% ([Google Environmental Report
2019](https://services.google.com/fh/files/misc/google_2019-environmental-report.pdf)).

| 2013 | 2014 | 2015 | 2016 | 2017 | 2018  |
| ---- | ---- | ---- | ---- | ---- | ----- |
| 3.7m | 4.4m | 5.2m | 6.2m | 7.6m | 10.1m |

At this level of consumption, it makes sense to do things like [build your own
servers from
scratch](https://www.wired.com/2016/05/googles-making-chips-now-time-intel-freak/).

The cloud providers can also dedicate significant capex to environmental goals.
Amazon, Google and Microsoft all have renewable energy projects which either
deliver energy directly to their facilities, or plug into the grid. [This
doesn’t mean they can run on 100% renewable
energy](https://davidmytton.blog/how-can-data-centers-use-100-renewable-electricity/),
but by being the largest purchasers of renewables and matching energy usage with
renewables purchases in aggregate, they can benefit from lower prices.

Cloud vendors making these improvements is important because consumers tend not
to make buying decisions based on sustainability criteria. Price is more
important. As such, [organisations must force green choices as the
default](https://davidmytton.blog/shifting-the-sustainability-focus-from-the-individual-to-the-corporation/) and
best option, not just by environmental standards but by price and quality.
Customers should not have to choose between green or cheap. They should be able
to get both.

## Slowing efficiency improvements

No cloud vendor offers granular data solely for its cloud business. This makes
it difficult to compare like-for-like e.g. Amazon Total GHG Emissions include
its eCommerce shipping and logistics whereas Google which has minimal eCommerce
operations. [This is an area where additional transparency would be
beneficial](https://davidmytton.blog/sustainability-doesnt-work-without-transparency/).

Google has been carbon neutral globally since 2007 and has matched its energy
usage with renewables since 2017. In contrast, Microsoft has been carbon neutral
globally since 2012 and will match its energy usage by 2025. Amazon has the
worst environmental footprint: it plans to be carbon neutral by 2040 and matched
50% of its energy with purchases of renewables in 2018, aiming for 100% by 2030.

Google has been the most transparent, probably because it has the most to boast
about. Microsoft announced greater reporting capabilities for its enterprise
Azure customers at the beginning of 2020, but Google seems to be pushing more
innovative approaches to [carbon aware
computing](https://davidmytton.blog/carbon-emissions-aware-cloud-compute/). It
has also made major improvements to the overall power usage effectiveness of its
data centres.

![Google PUE graph](google-pue.png "Google average power usage effectiveness
(PUE) for all data centers ([Environmental Report
2019](https://sustainability.google/reports/environmental-report-2019/))")

However, there is only so far that PUE can go. A PUE ratio of 1.0 would mean
that 100% of energy going into the data centre went to the IT equipment. This is
impossible because some energy is needed for cooling, lighting and power
distribution. Use of equipment like uninterruptible power supples involves
losses because nothing is 100% efficient.

And if you look to the industry in general, PUE values are much higher, and have
flatlined for some time. This is because older data centres are more difficult
(or not cost effective) to upgrade.

![Data center energy efficiency gains have flattened out](flat-pue.png "Data
center energy efficiency gains have flattened out ([Uptime
Institute](https://journal.uptimeinstitute.com/data-center-pues-flat-since-2013/))")

Industry trends mean there is significant uncertainty around future energy
usage. The past decade has been the decade of migration – swapping on-premise
physical servers and self-hosted VMs with cloud hosted instances, SaaS and IaaS.
There is still more to migrate but as the cloud is the new default, there is
less efficiency to be had just from migrations.

Deployment of new technologies may also overtake the migration to the cloud.
This has been the reasoning behind projections that we could see [data centre
energy
usage](https://davidmytton.blog/how-much-energy-do-data-centers-use/) grow from
1% to a range of 3-13% of global electricity by 2030 ([Andrae and Edler,
2015](https://doi.org/10.3390/challe6010117)).

70% of the global population are projected to have access to mobile connectivity
by 2023 ([Cisco,
2020](https://www.cisco.com/c/en/us/solutions/collateral/executive-perspectives/annual-internet-report/white-paper-c11-741490.html)) and
70% of YouTube streaming hours are already on smartphones and tablets ([Google,
2018](https://www.thinkwithgoogle.com/data/global-youtube-mobile-watch-time-statistics/)). 5G
is expected to account for 10% of global mobile devices by 2023 ([Cisco,
2020](https://www.cisco.com/c/en/us/solutions/collateral/executive-perspectives/annual-internet-report/white-paper-c11-741490.html)) and
5G base station power usage expected to x3 higher than 4G base
stations ([Koziol,
2019](https://spectrum.ieee.org/telecom/wireless/5gs-waveform-is-a-battery-vampire)).

How much energy will machine learning use with new types of chips? What about
the end of Moore’s Law ([Huang,
2015](https://spectrum.ieee.org/semiconductors/design/the-death-of-moores-law-will-spur-innovation))
and the deployment of large numbers of IoT sensors? What about edge compute?

> Hyperscale data centers are often in regions with abundant access to renewable
> energy, such as Google’s Finland data center ([Google,
> 2018](https://storage.googleapis.com/gweb-sustainability.appspot.com/pdf/24x7-carbon-free-energy-data-centers.pdf)).
> However, these locations tend to be away from population centers which means
> higher network response times as data must travel further to the end-user. As
> urbanisation increases, the need for low latency will require data centers to
> be sited closer to the user ([Kass and Ravagni,
> 2019](https://www.sdg-dc.com/)) but these locations may be less suitable for
> access to renewable sources of electricity or natural water sources for
> cooling.
>
> <cite>[How much energy do data centers
> use?](https://davidmytton.blog/how-much-energy-do-data-centers-use/)</cite>

## Losing control of edge facilities

When you look at the details of Google’s improvements, they are only including
the 15 facilities they own in their measurement scope.

![Table of Google PUE figures](google-pue-2020.png "Google data centre yearly
PUE performance report ([Google
2020](https://www.google.com/about/datacenters/efficiency/))")

This does not include the facilities that Google runs equipment in, but doesn’t
own. You just need to look at their edge network map to see how many that is.
Google has presence in 90 internet exchanges and 100 interconnection facilities,
plus hundreds of additional edge nodes in metro areas.

![Map of Google's POPs](google-edge-pops.png "[Google’s Edge Points of Presence
(POPs)](https://peering.google.com/#/infrastructure)")

![Map of Google's edge nodes](google-edge-nodes.png "[Google Edge
Nodes](https://peering.google.com/#/infrastructure)")

Placing content closer to the user is necessary to reduce latency and improve
things like loading times for YouTube videos. It can also improve energy
efficiency because the content must only be fetched once from the central
repository, then accessed locally for each subsequent user.

However, the downside is the lack of control over the facilities where equipment
is located. The edge PoPs in internet exchanges are usually run by the large
colocation vendors such as Equinix and Digital Realty. Edge Nodes are more
likely to be in ISP facilities, much closer to the user.

Whilst Google buys 100% renewable energy to match its own electricity usage, it
does not break out whether that is just for its own facilities or whether it
includes 3rd party colocation as well. For example, Equinix runs over 200 data
centres including many of the internet exchanges that Google might colocate its
equipment.

Energy consumption from electricity and chilled water ([Equinix Sustainability
Report
2019](https://www.equinix.com/resources/infopapers/corporate-sustainability-report/)):

|                          | 2015 | 2016  | 2017  | 2018  | 2019  |
| ------------------------ | ---- | ----- | ----- | ----- | ----- |
| Energy consumption (MWh) | 2.6m | 3.72m | 4.54m | 5.18m | 5.74m |
| % renewable              | 34%  | 56%   | 77%   | 91%   | 92%   |

It is unclear whether Google includes the electricity consumption it pays for
from 3rd party colocation vendors, such as Equinix, in its environmental
reporting. This should be covered by Google’s Scope 2 or Scope 3 reporting,
depending on whether it contracts directly for the electricity (scope 2) or
whether it is contracted by a 3rd party (scope 3). If Google is including them
in scope 3 then it is not offsetting those emissions, because its offsets are
only purchased for scope 1 + scope 2 + scope 3 “business travel and commuting”.
Scope 3 “other” is excluded.

There are also [significant regional
differences](https://sustainability.equinix.com/wp-content/uploads/2020/05/GU_IBX-Sustainability-Quick-Reference_US-EN-3.pdf),
such as the majority of Equinix’s North American facilities listed as being
covered by 100% renewables but 0% coverage for many of the South American
facilities. The picture gets worse as you move away from the hyperscale cloud
vendors (even with AWS’s poor environmental credentials).

![Graph of renewable energy in Virginia-based data
centers](dirty-data-or-clicking-clean-graph.png "Clicking Clean Virginia
([Greenpeace
2019](https://www.greenpeace.org/usa/reports/click-clean-virginia/))")

## Energy efficient edge compute and serverless

The traditional approach to compute is to buy servers or VMs. The server sits
there and waits to serve traffic. Its power draw is loosely correlated to the
CPU load, although this has been improving in recent years. Even so, utilisation
of servers is poor – only 50% in the best, hyperscale facilities ([Masanet et
al,
2013](https://eta.lbl.gov/publications/energy-efficiency-potential-cloud); [Shehabi
et al,
2016](https://eta.lbl.gov/publications/united-states-data-center-energy)). This
translates to 40,000 GWh/yr in direct server electricity consumption in the US
as of 2020, of which half can be wasted by idle servers ([Shehabi et al,
2016](https://eta.lbl.gov/publications/united-states-data-center-energy)).

Event driven architectures change this.

Serverless functions spin up in response to incoming events and you are billed
only for the resources used during the execution time. When the function is no
longer in use, the resources are reallocated elsewhere (although the instance
may stick around for a period of idle time in case another event comes in).

This incentivises more efficient resource usage and provides granular reporting
on a function level – you can see which functions take up the most execution
time, which equals money. This is essentially a proxy for energy usage. For the
first time, we have unit of compute which can directly incentivise more energy
efficient software engineering.

The same thing can apply to containers. Although they tend to run more like VMs
and servers, they are much more lightweight and have a much shorter lifespan.
You normally only install the minimum dependencies for your application and
because they do not emulate a full system, they start up much faster. This
allows for fast scaling up, but also allows for downscaling when those resources
are no longer needed.

![Graph of average container lifecycles](average-container-lifecycles.png "Average Container Lifetimes ([Datadog,
2019](https://www.datadoghq.com/container-report/))")

It becomes more complex when you need to access large datasets on persistent
storage, but for stateless applications, you could have units of compute [move
around the globe based on access to lower carbon sources of
energy](https://davidmytton.blog/carbon-emissions-aware-cloud-compute/). This
already happens for distributing traffic based on load and spot markets allow
workload optimisation based on price.

## The right edge at the right time

A long time ago, fitting programs into memory was a big challenge. Hardware was
expensive and available memory limited. As hardware became cheaper, programmers
had to think less about efficient use of computer resources. We can see this on
the web as the average size of web pages has increased over the last 10 years.

![Average webpage sizes](webpage-sizes.png "Average webpage sizes 2011 – 2020
([HTTP Archive](https://httparchive.org/reports/page-weight))")

With PUE values unlikely to get much closer 1.0 in hyperscale data centres and
already plateauing in other facilities, centralised cloud compute has almost
reached its efficiency limits.

Edge compute is not designed to replace centralised cloud compute – it
supplements it. Use cases typically revolve around low-latency, such as machine
learning at the edge, or for processing large volumes of data without incurring
backhaul data fees. Energy (cost) savings are another use case. [Serverless
platforms](https://davidmytton.blog/who-has-the-best-serverless-platform/) are
particularly well designed to quickly return responses to requests by offloading
the processing to edge nodes.

Improved compute power and the availability of edge platforms such
as [Cloudflare Workers and StackPath Serverless
Scripting](https://davidmytton.blog/who-has-the-best-serverless-platform/) (StackPath
acquired my company in 2018) means there will be a focus on large numbers of
smaller edge points of presence. Their smaller scale means resources are more
expensive, so it doesn’t make sense to deploy heavy duty servers which are never
fully utilised. Vendors can optimise their PoP footprint by more efficiently
scheduling container and serverless workloads. Unlike a VM which requires
reserved capacity (unless you oversell), serverless and container workloads can
be scheduled the resources as they are needed.

Data centre energy projections have been wrong in the past ([Malmodin and
Lundén, 2018](https://doi.org/10.3390/su10093027); [Jones,
2018](https://doi.org/10.1038/d41586-018-06610-y); [Masanet et al,
2019](https://doi.org/10.1038/s41558-019-0535-4)). We want to encourage more
energy efficient use of resources but [encouraging the right behaviour depends
on the right
incentives](https://davidmytton.blog/innovation-in-incentives-how-should-startups-structure-salaries-bonuses-commission-stock-options/).
Efficient usage of premium resources is important, and efficient compute is a
proxy for energy. Now energy usage is linked to price, the incentives are
finally aligned. Edge compute could be where we start to see innovations in
resource, and therefore energy, efficiency.
