---
title: "Carbon emissions aware cloud compute"
date: 2020-04-27
modified: 2020-04-27
draft: false
tags: ["IT Energy", "Data Center Energy", "Carbon Awareness", "Cloud"]
summary: "The first example of carbon aware compute is uniquely suited to 
hyperscale cloud environments. It becomes even more interesting with carbon 
aware load balancing and serverless."
url: carbon-emissions-aware-cloud-compute
---

On 22 April, [Google
announced](https://blog.google/inside-google/infrastructure/data-centers-work-harder-sun-shines-wind-blows) it
is now optimising compute workloads based on the carbon intensity of data center
electricity. This means it is scheduling some compute jobs to run when it has
access to the most renewable electricity.

Google has been carbon neutral since 2007 and has matched 100% of its
electricity usage with purchases of renewable electricity since 2017, but [that
does not mean it is actually using 100% renewable
electricity](https://davidmytton.blog/how-can-data-centers-use-100-renewable-electricity/).

This is the same as your home electricity. Even if you are on a 100% renewable
electricity tariff, you are not always using renewable electricity. It just
means that your supplier procures 100% renewably sourced electricity into the
grid, but the grid has multiple sources of electricity. Electrons are electrons
and there are [few countries which generate all their electrons from 100%
renewable
sources](https://en.wikipedia.org/wiki/List_of_countries_by_renewable_electricity_production) (basically
just Iceland). Even those that do may import some electricity when demand is
high from interconnections with other countries which use non-renewable sources.

![Graph of renewables share of power generation by
region](renewables-share-of-power-generation-by-region.png "[Renewables share of
power generation by region, BP Energy Outlook
2019](https://www.bp.com/en/global/corporate/energy-economics/energy-outlook/demand-by-fuel/renewables.html)")

Until we get to a position where the majority of electricity is generated
renewably, the carbon intensity of supply is an important metric. This changes
on a minute by minute basis depending on what generating capacity is online,
which varies by region and country.

Over the last 3 months in the UK, the carbon intensity of electricity has ranged
from ~293g/kWh on 4th March (when gas was generating over 50% of supply) to a
low of ~61g/kWh on 21st April (when gas was generating around 17% and wind +
solar made up over 50% of supply).

![Graph of 3 month UK electricity generation](uk-electricity.png "[3 month UK
electricity generation, Electric
Insights](https://electricinsights.co.uk/#/dashboard?period=3-months&start=2020-01-26&&_k=urjlm9)")

You will also notice that price tends to be lower when renewables are high.
Historically, non-renewables have been cheaper than renewables because they are
a mature technology. Their main cost after deployment is the fuel.

However, we have now progressed wind and solar technology to the point where
their [levelised
cost](https://en.wikipedia.org/wiki/Levelized_cost_of_energy) is coming in lower
than non-renewables. [Carbon pricing is pushing non-renewable fuel costs
higher](https://www.carbonbrief.org/analysis-global-coal-power-set-for-record-fall-in-2019) and
they are having to compete with renewables which have no fuel costs at all.

![Table of LCOE](uk-lcoe.png "[Estimated UK LCOE for projects starting in 2015,
£/MWh,
Wikipedia.](https://en.wikipedia.org/wiki/Cost_of_electricity_by_source#United_Kingdom)")

Indeed, this comparison table is out of date. [The latest offshore wind auction
in the UK awarded LCOE strike prices of
£39/MWh](https://www.gov.uk/government/publications/contracts-for-difference-cfd-allocation-round-3-results/contracts-for-difference-cfd-allocation-round-3-results).
That’s very low!

## What does this mean for carbon emissions aware cloud compute?

Google is now scheduling its latency-insensitive workloads to correlate with
periods of low carbon intensity.

> We designed and deployed this first-of-its kind system for our hyperscale
> (meaning very large) data centers to shift the timing of many compute tasks to
> when low-carbon power sources, like wind and solar, are most plentiful. This
> is done without additional computer hardware and without impacting the
> performance of Google services like Search, Maps and YouTube that people rely
> on around the clock. Shifting the timing of non-urgent compute tasks—like
> creating new filter features on Google Photos, YouTube video processing, or
> adding new words to Google Translate—helps reduce the electrical grid’s carbon
> footprint, getting us closer to 24×7 carbon-free energy
>
> <cite>[Our data centers now work harder when the sun shines and wind
> blows](https://blog.google/inside-google/infrastructure/data-centers-work-harder-sun-shines-wind-blows)</cite>

The idea is that time-insensitive processing can be scheduled for a more
environmentally friendly time. This is not a new concept.

Papers from [Berl et al, 2010](https://doi.org/10.1093/comjnl/bxp080), [Buyya et
al, 2010](https://arxiv.org/abs/1006.0308), [Gelenbe,
2012](https://doi.org/10.1145/2168697.2168698), [Gao et al,
2013](https://doi.org/10.1109/INFCOM.2013.6566827), [Berrel et al,
2014](https://doi.org/10.1109/ICDCS.2014.53) and [Basmadjia,
2019](https://doi.org/10.3390/en12173301) have proposed “follow-the-renewables”
type systems. These use carbon intensity data and/or generation stats to
schedule workloads in locations where the carbon intensity is lowest.

The problem is that when you move from running your own data centers to using
abstracted units of compute running in a hyperscale data center owned by the
likes of Amazon, Google and Microsoft, you also lose all visibility into the
energy usage. If you buy a server and rack it into a colo facility, you can
measure the power draw from the physical rack and you get a bill for your
electricity each month. When you move to the cloud, you only get a bill for the
compute time.

With a significant part of the [1% of global electricity consumed by data
centers](https://davidmytton.blog/how-much-energy-do-data-centers-use/) being
from hyperscale, cloud facilities, the lack of carbon intensity data makes it
impossible to schedule your workloads in the most environmentally friendly way.

## Carbon emissions aware products

A major challenge with renewables like solar and wind is intermittency. We have
no control over when they will generate. This can result in some [strange
scenarios where we have to pay generators not to generate, due to system
capacity
issues](https://www.carbonbrief.org/why-windfarms-get-paid-to-switch-off). The
media love these negative stories about renewables but this is how the system
has to work in the short term whilst [transmission capacity is
upgraded](https://en.wikipedia.org/wiki/Western_HVDC_Link).

We can already see the beginnings of pricing aware products in the consumer
space. The UK electricity supplier, Octopus Energy, has a beta
“[Agile](https://octopus.energy/agile/)” tariff which in some cases has been
paying customers to use electricity. Rather than paying a fixed £/kWh, your
electricity price changes based supply and demand.

As with any market, when supply exceeds demand, prices fall. Sometimes they go
negative. The Octopus Agile tariff is one of the first to offer those savings
back to the consumer.

However, these kind of pricing events tend to happen at inconvenient times like
the middle of the night. It is no good being paid to use electricity if you are
asleep and cannot take advantage of it! Octopus are interesting because [they
have an API](https://www.youtube.com/watch?v=1Xb2BG0ctJ4&feature=emb_title) that
allows you to integrate your devices to automatically take advantage of this.

Devices are starting to become smarter with how they use energy. [Apple
introduced optimised charging in iOS
13](https://support.apple.com/en-us/HT210512) which learns your habits and
manages the charging completion time to correlate with when you wake up and
start using your phone. This is to optimise the battery life, but you can
imagine similar use cases with electricity pricing. Using pricing data to charge
when it is cheap is the next step (and you can already do it with the [Octopus
IFTTT smart plug integration](https://octopus.energy/ifttt/)).

The major cloud providers already offer spot market type pricing. [Amazon’s
complex spot markets](https://aws.amazon.com/ec2/spot/) allow you to bid for
instances. Google does this slightly differently with their [sustained use
discounts](https://cloud.google.com/compute/docs/sustained-use-discounts) which
apply automatically for sustained usage. [Preemptible
instances](https://cloud.google.com/compute/docs/instances/preemptible) have
significantly lower prices if you accept the tradeoff of instances terminating
with only a few seconds notice. These are priced based on supply and demand but
what about pricing based on carbon intensity as well?

Price signals are a fundamental feature of market economies. Carbon emissions
aware products should be no different. Google is using emissions data because it
owns its facilities. It does not necessarily need to expose that emissions data
to its cloud customers. Why would customers want to try and build their own
system when it could just be built into the price? We are used to paying
different fees based on the cloud region e.g. [networking is more expensive in
Australia than the
US.](https://blog.cloudflare.com/bandwidth-costs-around-the-world/) The carbon
cost of electricity should be built into the price paid for cloud resources in
the same way.

## Carbon aware serverless

Where this becomes more interesting is with [serverless
products](https://davidmytton.blog/who-has-the-best-serverless-platform/).
Despite the [advances in live migration of compute
VMs](https://cloud.google.com/compute/docs/instances/live-migration), there are
still challenges with moving large scale compute workloads to respond to price
or carbon signals. If VMs have to be stopped or large volumes of data migrated,
other costs come into play.

A big advantage of serverless is how it scales with demand, both up and down.
Even with cold start times, serverless functions start up much faster than VMs.
Code can be deployed globally but spin up only when traffic is directed at it.

Load balancing is used to distribute traffic. This can be as simple as evenly
splitting traffic across a cluster of machines but the more advanced algorithms
take customer location and cluster load into account.

Imagine if you could combine carbon aware load balancing with serverless
functions. The load balancing would be aware of the carbon intensity of each
region and direct traffic to serverless functions ready to accept traffic in the
region with the lowest carbon cost.

This would not work well if a user in Tokyo was directed to a server in New
York: the latency would be very high. However, carbon intensity is very local.
For a user in London, it might be better to route traffic to a data center
Edinburgh during a time of high wind in Scotland. Latency would be higher, but
the different would be negligible.

## Predicting carbon futures

All this works when you have real-time price signals for what is happening now,
but what about future pricing? Knowing whether to charge your laptop now is
quite different from knowing whether to start a 12 hour processing job,
especially if the job requires lots of data to be moved.

Google is combining two data sources to predict carbon intensity and schedule
jobs in advance.

> One of the forecasts, provided by our
> partner [Tomorrow](https://www.tmrow.com/), predicts how the average hourly
> carbon intensity of the local electrical grid will change over the course of a
> day. A complementary Google internal forecast predicts the hourly power
> resources that a data center needs to carry out its compute tasks during the
> same period. Then, we use the two forecasts to optimize hour-by-hour
> guidelines to align compute tasks with times of low-carbon electricity supply.
>
> <cite>[Our data centers now work harder when the sun shines and wind
> blows](https://blog.google/inside-google/infrastructure/data-centers-work-harder-sun-shines-wind-blows)</cite>

Although Google has not yet published its methodology, I expect they’re using
their internal cluster management system, Borg:

> Google’s Borg system is a cluster manager that runs hundreds of thousands of
> jobs, from many thousands of different applications, across a number of
> clusters each with up to tens of thousands of machines.
>
> <cite>[Large-scale cluster management at Google with Borg, Verma et al
> (2015)](https://dl.acm.org/doi/10.1145/2741948.2741964)</cite>

This allows scheduling of jobs over a period of time:

> Priority expresses relative importance for jobs that are running or waiting to
> run in a cell. *Quota* is used to decide which jobs to *admit* for scheduling.
> Quota is expressed as a vector of resource quantities (CPU, RAM, disk, etc.)
> at a given priority, for a period of time (typically months). The quantities
> specify the maximum amount of resources that a user’s job requests can ask for
> at a time (e.g., “20TiB of RAM at prod priority from now until the end of July
> in cell xx”). Quota-checking is part of admission control, not scheduling:
> jobs with insufficient quota are immediately rejected upon submission.
>
> <cite>[Large-scale cluster management at Google with Borg, Verma et al
> (2015)](https://dl.acm.org/doi/10.1145/2741948.2741964)</cite>

The concept of quota is important because it reflects the availability and cost
of resources:

> Higher-priority quota costs more than quota at lower- priority.
> Production-priority quota is limited to the actual resources available in the
> cell, so that a user who submits a production-priority job that fits in their
> quota can expect it to run, modulo fragmentation and constraints. Even though
> we encourage users to purchase no more quota than they need, many users
> overbuy because it insulates them against future shortages when their
> application’s user base grows. We respond to this by over-selling quota at
> lower-priority levels: every user has infinite quota at priority zero,
> although this is frequently hard to exercise because resources are over-
> subscribed. A low-priority job may be admitted but remain pending
> (unscheduled) due to insufficient resources.
>
> Quota allocation is handled outside of Borg, and is inti- mately tied to our
> physical capacity planning, whose results are reflected in the price and
> availability of quota in differ- ent datacenters. User jobs are admitted only
> if they have suf- ficient quota at the required priority.
>
> <cite>[Large-scale cluster management at Google with Borg, Verma et al
> (2015)](https://dl.acm.org/doi/10.1145/2741948.2741964)</cite>

If a cost is expressed in a dollar amount, it can also be expressed as a carbon
amount. You can then optimise for which you care about most, depending on the
priority of the job and perhaps even an [internal carbon tax for your business
unit](https://blogs.microsoft.com/on-the-issues/2019/04/15/were-increasing-our-carbon-fee-as-we-double-down-on-sustainability/).

> One of Borg’s primary goals is to make efficient use of Google’s fleet of
> machines, which represents a significant financial investment: increasing
> utilization by a few percent- age points can save millions of dollars.
>
> <cite>[Large-scale cluster management at Google with Borg, Verma et al
> (2015)](https://dl.acm.org/doi/10.1145/2741948.2741964)</cite>

Google is currently doing carbon aware scheduling in a single data center but
the plan is to allow location-aware scheduling. This is much closer to the
approaches described in the research papers noted above. [Calculating the carbon
intensity for each country is
complex](https://www.youtube.com/watch?v=PAelZb2ZYwI).

This is perhaps the first large-scale example of carbon aware compute and is
uniquely suited to hyperscale cloud environments. Even if one were to implement
a “follow-the-renewables” approach, there are few companies with the scale for
it to make much difference. It is easy to see why these papers have remained of
academic interest only.

Cloud computing changes that. Google is the smallest of the big three cloud
providers, yet making these optimisations are still in its interest and result
in millions of dollars of savings, and carbon reductions. Building this into the
public cloud compute offerings means even the smallest user can access
environmentally friendly compute resources.
