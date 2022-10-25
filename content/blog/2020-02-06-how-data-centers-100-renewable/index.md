---
title: "How can data centers use 100% renewable electricity?"
date: 2020-02-06
modified: 2020-09-18
draft: false
tags: ["Data Center Energy"]
summary: "If we still generate energy from non-renewable sources, how can a 
data center be 100% renewable? What does 100% renewables and sustainability 
mean for data centers and the cloud?"
url: how-can-data-centers-use-100-renewable-electricity
---

Data centers have [a range of
components](https://davidmytton.blog/how-much-energy-do-data-centers-use/) which
make up their energy footprint, but [electricity is the primary energy
input](https://www.iea.org/commentaries/data-centres-and-energy-from-global-headlines-to-local-headaches) in
daily operations. All the equipment – servers, storage, networking – is powered
by electricity, which means the environmentally impact of a data center is
largely dependent on where that electricity comes from.

![Global data center energy end use (IEA,
2020).](global-data-center-electricity-usage.png "Global data center energy end
use ([IEA,
2020](https://www.iea.org/data-and-statistics/charts/global-data-centre-energy-demand-by-end-use)).")

A large proportion of data center usage today is through the cloud. It is
estimated that [53% of all servers will be located in hyperscale cloud data
centers by
2021](https://www.cisco.com/c/en/us/solutions/collateral/service-provider/global-cloud-index-gci/white-paper-c11-738085.html).
This basically means AWS, Google Cloud or Microsoft Azure.

Whilst non-renewables continue to make up a large part of the source of that
electricity, a transition is in progress to clean up the grid.

{{< twitter user="iain_staffell" id="1213942160862695425" >}}

The UK has been rapidly decarbonising but global progress varies widely.

![Renewables share of power generation by region (BP,
2019).](renewables-share-of-power-generation-by-region.png "Renewables share of
power generation by region ([BP,
2019](https://www.bp.com/en/global/corporate/energy-economics/energy-outlook/demand-by-fuel/renewables.html)).")

Most data centers plug directly into the local electricity grid and in most
countries, non-renewables [still make up a significant part of the electricity
mix](https://www.electricinsights.co.uk/). This is relevant to data center
electricity usage because it is not possible to guarantee 100% renewables if
their electricity is sourced from the grid. When renewables are not
generating, [electricity must be sourced from other
means](https://www.ft.com/content/d75f49d0-103f-11ea-a225-db2f231cfeae) and
utilities have to make up their commitments through offsets or purchases of
renewables elsewhere.

## Cloud data center renewable electricity today

[Google](https://services.google.com/fh/files/misc/google_2019-environmental-report.pdf) and [Microsoft](https://blogs.microsoft.com/blog/2020/01/16/microsoft-will-be-carbon-negative-by-2030/) are
are both carbon neutral companies. This is different from “net zero”, which
Microsoft explains well on their blog:

> Given common usage, companies have typically said they’re “carbon neutral” if
> they offset their emissions with payments *either* to avoid a reduction in
> emissions *or* remove carbon from the atmosphere. But these are two very
> different things. For example, one way to avoid a reduction in emissions is to
> pay someone not to cut down the trees on the land they own. This is a good
> thing, but in effect it pays someone *not* to do something that would have a
> negative impact. It doesn’t lead to planting more trees that would have a
> positive impact by removing carbon.
>
> In contrast, “net zero” means that a company actually removes as much carbon
> as it emits. The reason the phrase is “net zero” and not just “zero” is
> because there are still carbon emissions, but these are equal to carbon
> removal. And “carbon negative” means that a company is removing more carbon
> than it emits each year.
>
> <cite>[Microsoft Blog, 2020.](https://blogs.microsoft.com/blog/2020/01/16/microsoft-will-be-carbon-negative-by-2030/)</cite>

When a data center is connected to a grid with a varying mix, operators
currently have two options:

1. **Purchase offsets** by making payments to projects to match your total
   emissions.
2. **Contract energy** from renewables sources to match your total energy
   consumption, even if those sources are elsewhere on the grid (or even in
   different countries).

The first of these options is what Google has been doing since 2007 and
Microsoft since 2012. This makes them carbon neutral.

The next step is to match like-for-like rather than matching emissions for
emissions e.g. buy renewable energy to match all your energy usage. [Google has
been doing this since
2017](https://www.blog.google/outreach-initiatives/environment/meeting-our-match-buying-100-percent-renewable-energy/) and [Microsoft
has
pledged](https://blogs.microsoft.com/blog/2020/01/16/microsoft-will-be-carbon-negative-by-2030/) to
do this by 2025. Microsoft is actually already doing this for electricity, but
not for *energy* ([In
FY2018](http://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE3455q) 391,047
MWh still came from other fuels such as jet fuel, natural gas, diesel, etc).

Amazon is more difficult to assess because they provide only limited
environmental reporting. [5 of their 22 cloud regions are carbon
neutral](https://aws.amazon.com/about-aws/sustainability/). They [have a
goal](https://press.aboutamazon.com/news-releases/news-release-details/amazon-co-founds-climate-pledge-setting-goal-meet-paris) to
be completely carbon neutral as a business by 2040, claim to use more than [50%
of renewables as of
2018](https://aws.amazon.com/about-aws/sustainability/sustainability-timeline/),
and are aiming to be 100% renewables by 2030.

Overall, this second option has resulted in the tech industry being the largest
corporate purchaser of renewable energy.

![Top corporate renewables off-takers (IEA,
2019).](top-corporate-purchases-renewables.png "Top corporate renewables
off-takers ([IEA,
2019](https://www.iea.org/commentaries/data-centres-and-energy-from-global-headlines-to-local-headaches)).")

## A third option – 24/7 local renewables

The problem with contracting energy is it is sort of cheating. Whilst renewable
energy is being generated somewhere, that may not be where your data center is.
The third option is to fix this – deploy renewable sources of energy on the
local grid providing power 24/7, so the data center will actually consume
renewables at all times.

This is much more difficult because of the varying location of data centers.
Some facilities are located in regions with abundant wind, solar and/or hydro.
Others are not.

[Google started work achieve 24/7 renewables in
2018](https://www.blog.google/outreach-initiatives/sustainability/internet-24x7-carbon-free-energy-should-be-too/).
It is approaching this through construction of its own, or contracting with 3rd
parties for, renewable sources of energy that go directly into the local
grid. [Google published a paper about their
approach](https://storage.googleapis.com/gweb-sustainability.appspot.com/pdf/24x7-carbon-free-energy-data-centers.pdf) which
includes some interesting visualisations of the concept.

For example, compare a theoretical 24/7 100% renewables data center:

![Every hour of electricity use at a 24x7 carbon-free data
center](google-theoretical-100-renewables.png "Every hour of electricity use at
a 24×7 carbon-free data center ([Google,
2018](https://storage.googleapis.com/gweb-sustainability.appspot.com/pdf/24x7-carbon-free-energy-data-centers.pdf)).")

With an actual data centre in Finland which is able to source 97% renewables:

![Every hour of electricity use at Finland data
center](google-finland-renewables.png "Every hour of electricity use at Finland
data center ([Google,
2018](https://storage.googleapis.com/gweb-sustainability.appspot.com/pdf/24x7-carbon-free-energy-data-centers.pdf)).")

And an actual data center in The Netherlands with 69% renewables, and a solar
source of energy added part-way through the year.

![Every hour of electricity use at Netherlands data
center](google-netherlands-renewables.png "Every hour of electricity use at
Netherlands data center ([Google,
2018](https://storage.googleapis.com/gweb-sustainability.appspot.com/pdf/24x7-carbon-free-energy-data-centers.pdf)).")

The goal of 24/7 100% renewables is informing how Google procures
energy. [Having contracted for 350MW of solar
energy](https://www.greentechmedia.com/articles/read/google-inks-huge-ci-deal-in-nevada-with-a-prominent-place-for-storage) at
a new data center being constructed in Las Vegas, Google has also bought
250-280MW of storage. This means Google can store renewably generated energy
that is available on-demand when renewables are not available locally.

## How can data centers use 100% renewable electricity?

As a result of these various activities, the answer to this question has
progressed over time.

The first step has been to offset. This is followed by matching usage with
like-for-like energy purchases somewhere. The final stage is direct consumption
of locally generated renewables, either in real time or stored from recent
generation.

So the next time you see a tech company announcing a huge renewables project,
you should look to see exactly what that mean and where that energy will really
go. New renewables are good, but whether that energy is actually powering the
company operations directly is another question.

For more on this, [this episode of the The Interchange
podcast](https://www.greentechmedia.com/articles/read/24-7-renewables-the-emerging-art-of-matching-renewables-with-demand) discusses
the details.
