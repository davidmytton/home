---
title: "How much water do data centers use?"
date: 2020-06-10
modified: 2021-02-16
draft: false
tags: ["Data Center Energy", "IT Energy", "Data Center Water", "Cloud"]
summary: "US data centers are expected to use 660 billion litres of water in 
2020. In 2018, Google consumed 15.79bn litres and Microsoft 3.61bn litres, 
2021. primarily for their data centers. What is this used for and how does it 
2022. impact the environment?"
url: how-much-water-do-data-centers-use
---

**Update:** [An updated, expanded, and peer-reviewed version of this blog
post](https://doi.org/10.1038/s41545-021-00101-w) was published in the open
access journal npj Clean Water in Feb 2021.

---

There are several components which make up environmental footprint of a data
center. [Energy
usage](https://davidmytton.blog/how-much-energy-do-data-centers-use/) is a big
one – 1-1.5% of global electricity usage – but it is not the only one. Water is
also a factor.

In FY18, Google used 15.79 billion litres of water ([Google,
2019](https://services.google.com/fh/files/misc/google_2019-environmental-report.pdf)).
Some went to offices, but the majority was consumed by its global fleet of data
centers. In FY18, Microsoft used 3.5 billion litres ([Microsoft,
2018](http://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE3455q)), also
with the majority going to its data centers.

This is important because water availability is a major concern in the context
of climate change. Global water use has increased by x6 over the past 100 years,
continues to grow by 1% every year ([UN,
2020](https://unesdoc.unesco.org/ark:/48223/pf0000372985.locale=en)), and many
areas suffer from water stress.

![World map showing water stress](annual-water-stress.png "Annual baseline water
stress ([UN,
2020](https://unesdoc.unesco.org/ark:/48223/pf0000372985.locale=en)).")

Water is essential to achieving the climate targets because climate change
affects the availability, quality and quantity of water for basic needs such as
industry and agriculture ([UN,
2020](https://unesdoc.unesco.org/ark:/48223/pf0000372985.locale=en)). It is also
subject to a specific Sustainable Development
Goal: [SDG6](https://sustainabledevelopment.un.org/sdg6) – ensure availability
and sustainable management of water and sanitation for all.

Projections suggest that demand for water will increase by 55% between 2000 and
2050 due to growth from manufacturing (+400%), thermal power generation (+140%)
and domestic use (+130%) ([OECD,
2012](https://doi.org/10.1787/9789264122246-en)).

So what do data centers use water for? This post will examine where data centers
use water and what that means for the environment.

## Data center water use

US data centers used 626 billion litres of water in 2014, projected to grow to
660 billion litres in 2020 ([Shehabi et al,
2016](https://eta.lbl.gov/publications/united-states-data-center-energy)). This
is split across two main categories: electricity generation and cooling.

Water use in electricity was x4 greater than that used on-site for cooling: 7.6
litres of water is used for every 1 kWh of electricity generated compared to 1.8
litres per kWh of total data center site energy use ([Shehabi et al,
2016](https://eta.lbl.gov/publications/united-states-data-center-energy)).
However, this is based on water consumption in US power production in 2003 so
does not consider the impact of the decarbonisation of the electricity grid
since then.

![Graph of direct vs. indirect U.S. Data Center Water
Consumption](us-dc-water-consumption.png "Direct vs. Indirect U.S. Data Center
Water Consumption ([Shehabi et al,
2016](https://eta.lbl.gov/publications/united-states-data-center-energy)).")

### Water use in electricity generation

The electricity used to power data centers requires significant volumes of
water. Power plants burn fuel to heat water, generating steam to turn a turbine
which then generates electricity. You often see the results from the huge
cooling towers next to power plants.

The same happens in nuclear power plants where the heat is generated through
nuclear fission. Hydroelectricity also relies on water (although it does not
“consume” the water because it can be passed on to downstream users).

Only solar and wind do not involve water in the generation – instead the
manufacturing process contributes the majority of the water footprint.

![Chart of water footprint and carbon
intensity](water-footprint-carbon-intensity-of-energy-production-by-source.png "Indicative water footprint and carbon intensity of energy production, by source
([UN, 2020](https://unesdoc.unesco.org/ark:/48223/pf0000372985.locale=en)).")

Although the IT industry reports x6 more compute instances, x10 more network
traffic and x25 more storage capacity in 2018 compared to 2010, data centre
energy consumption has only grown by 6% ([Masanet et al,
2020](https://doi.org/10.1126/science.aba3758)).

This is helped by the move to the cloud. 53% of servers are expected to be in
hyperscale facilities by 2021 ([Cisco,
2018](https://www.cisco.com/c/en/us/solutions/collateral/service-provider/global-cloud-index-gci/white-paper-c11-738085.html))
and cloud vendors are some of the largest purchasers of renewable electricity
([IEA,
2019](https://www.iea.org/commentaries/data-centres-and-energy-from-global-headlines-to-local-headaches)).
If the electricity is generated from wind and solar – [which is not yet possible
100% of the
time](https://davidmytton.blog/how-can-data-centers-use-100-renewable-electricity/) –
then the water footprint is significantly reduced.

Water is a binary resource: it is either used or not used. This is different
from non-renewable electricity generation which can at least be offset.
Switching to renewable sources is the only way to reduce the impact of this
water consumption in this category.

### Water use in data center cooling

Think how often you hear the fans on your computer spin up. IT equipment
generates a lot of heat and must be kept cool to operate efficiently. Drawing
cool air over the hot metal components transfers the heat energy to the air,
which is then pushed out of the computer. This works because the computer
temperature is usually higher than the surrounding air.

![Photo of Google cooling towers](google-chillers.jpg "Steam rises above the
cooling towers in The Dalles data center in Oregon ([Google,
2020](https://www.google.com/about/datacenters/gallery/)).")

The same happens in data centers, just at a much larger scale. Chillers exchange
the internal heat with the cooler external environment, or air is drawn in and
then cooled down. A 1MW data center using traditional cooling can use around
25.55 million litres of water per year ([Heslin,
2016](https://journal.uptimeinstitute.com/dont-ignore-water-consumption/)).

> Cooling towers cool warm condenser water from the chillers by pulling ambient
> air in from the sides, which passes over a wet media, causing the water to
> evaporate. The cooling tower then rejects the heat by blowing hot, wet air out
> of the top. The cooled condenser water then returns back to the chiller to
> again accept heat to be rejected.
>
> <cite>[Heslin, 2016.](https://journal.uptimeinstitute.com/dont-ignore-water-consumption/)</cite>

> Adiabatic economizers typically spray water onto heat exchanger surfaces or in
> some cases directly into the air stream. The water serves to cool the air as
> it enters the data center. In the process, however, some of the water
> evaporates and is lost. This means you need a reliable, continuous source of
> water for these systems to be effective.
>
> <cite>[Frizziero, 2018.](https://blog.se.com/datacenter/2018/05/10/why-water-use-consideration-cooling-data-center/)</cite>

The typical data center has tended to operate at temperatures of 20-22C, with a
lower bound of 12C ([Miller,
2011](https://www.datacenterknowledge.com/archives/2011/03/10/energy-efficiency-guide-data-center-temperature)).
As temperatures increase, equipment failure rates also increase. However,
experiments have shown that the failure rate does not grow linearly with
temperature ([Miller,
2008](https://www.datacenterknowledge.com/archives/2008/09/18/intel-servers-do-fine-with-outside-air)).

Raising the chiller temperature from the usual 7-10C to 18-20C can reduce
operational expenses by 40%, due to the reduction in energy required for
cooling. When designing new data centers, using smaller chillers can reduce
capex by up to 30% ([Frizziero,
2016](https://blog.se.com/datacenter/2016/08/17/water-temperatures-data-center-cooling/)).

Some [Google](https://www.datacenterknowledge.com/archives/2009/07/15/googles-chiller-less-data-center) and [Microsoft](https://www.datacenterknowledge.com/archives/2009/09/24/microsofts-chiller-less-data-center) data
centers have been operating with cooling just from at ambient air temperatures
since 2009 but this is not possible in hot environments.

## Measuring data center water usage

Power Usage Effectiveness is the metric used to report data center energy
efficiency. This is the ratio between power drawn by the infrastructure
components and power delivered to the servers, disks and networking equipment
([GHG Protocol,
2017](https://ghgprotocol.org/sites/default/files/GHGP-ICTSG%20-%20ALL%20Chapters.pdf)).

A PUE ratio of 1.0 would mean that 100% of energy going into the data centre
went to the IT equipment. This is impossible because some energy is needed for
cooling, lighting and power distribution. [Use of equipment like uninterruptible
power supples involves
losses](https://davidmytton.blog/how-much-energy-do-data-centers-use/) because
nothing is 100% efficient.

Cloud vendors are pushing these ratios very low – Google reports a Q1 2020
trailing twelve month PUE of 1.10 for the 15 facilities it owns ([Google,
2020](https://www.google.com/about/datacenters/efficiency/)).

[Water Usage Effectiveness
(WUE)](https://www.thegreengrid.org/en/resources/library-and-tools/238-Water-Usage-Effectiveness-%28WUE%29%3A-A-Green-Grid-Data-Center-Sustainability-Metric-) is
a similar metric for water. This is defined as the annual water usage divided by
the IT equipment energy, with units of litres/kilowatt hour (L/kWh). It covers
the operations, not the full life-cycle from construction to decommissioning.

However, less than a third of data center operators track any water metrics and
water conservation is ranked as a low priority ([Heslin,
2016](https://journal.uptimeinstitute.com/dont-ignore-water-consumption/)).
Facebook is one of the few companies to report their WUE ratio. They are very
transparent about its [overall environmental
footprint](https://sustainability.fb.com/sustainability-in-numbers/) and it even
has real time dashboards for
its [Lulea](https://www.facebook.com/LuleaDataCenter/app/115276998849912/), [Forest
City](https://www.facebook.com/ForestCityDataCenter/app/288655784601722/) and [Prineville](https://www.facebook.com/PrinevilleDataCenter/app/399244020173259/) data
centers. None of the big cloud vendors publish water efficiency metrics.

![Facebook Water Usage Effectiveness](facebook-wue.png "Facebook Water Usage
Effectiveness
([2020](https://sustainability.fb.com/sustainability-in-numbers/#section-Water)).")

### Google and Microsoft water usage

Although Google and Microsoft do not report WUE figures, they do report overall
water consumption. These are total consumption figures which include offices and
other facilities but consist primarily of water from data center operations.
However, they only represent direct water usage, not water used in electricity
generation.

| Company                | FY18           | FY17          | FY16          |
| ---------------------- | -------------- | ------------- | ------------- |
| Microsoft [^microsoft] | 3.61bn litres  | 1.9bn litres  |               |
| Google [^google]       | 15.79bn litres | 11.6bn litres | 9.46bn litres |

[^microsoft]:
    [Microsoft water
    consumption](http://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE3455q).
    Microsoft also notes that 50% of the change from FY17 to FY18 is from a
    change in methodology, the other 50% coming from organisational growth.

[^google]: <https://services.google.com/fh/files/misc/google_2019-environmental-report.pdf>

Both companies have good track records when it comes to working towards reducing
their carbon footprint and increasing use of renewable energy.

Google has been carbon neutral globally since 2007 and has matched its energy
usage with renewables since 2017 ([Google,
2020](https://www.google.com/about/datacenters/gallery/)). Microsoft has been
carbon neutral globally since 2012 and will match its energy usage by 2025
([Smith,
2020](https://blogs.microsoft.com/blog/2020/01/16/microsoft-will-be-carbon-negative-by-2030/)).
However, they do not publish as much about their water consumption as they do
with their energy and carbon footprints.

Microsoft [submits an annual report to
CDP](https://www.cdp.net/en/responses?utf8=%E2%9C%93&queries%5Bname%5D=microsoft&filters%5Byears%5D%5B%5D=2010&filters%5Byears%5D%5B%5D=2011&filters%5Byears%5D%5B%5D=2012&filters%5Byears%5D%5B%5D=2013&filters%5Byears%5D%5B%5D=2014&filters%5Byears%5D%5B%5D=2015&filters%5Byears%5D%5B%5D=2016&filters%5Byears%5D%5B%5D=2017&filters%5Byears%5D%5B%5D=2018&filters%5Byears%5D%5B%5D=2019&filters%5Byears%5D%5B%5D=2020&filters%5Bprogrammes%5D%5B%5D=Water),
a sustainability reporting charity which includes detailed metrics and
information about their water footprint (as well as other categories).

[Google submits reports for climate
change](https://www.cdp.net/en/responses?utf8=%E2%9C%93&queries%5Bname%5D=google&filters%5Byears%5D%5B%5D=2010&filters%5Byears%5D%5B%5D=2011&filters%5Byears%5D%5B%5D=2012&filters%5Byears%5D%5B%5D=2013&filters%5Byears%5D%5B%5D=2014&filters%5Byears%5D%5B%5D=2015&filters%5Byears%5D%5B%5D=2016&filters%5Byears%5D%5B%5D=2017&filters%5Byears%5D%5B%5D=2018&filters%5Byears%5D%5B%5D=2019&filters%5Byears%5D%5B%5D=2020) but
not for water. Perhaps this is because there is significant controversy around
Google’s data center water consumption:

> Google considers its water use a proprietary trade secret and bars even public
> officials from disclosing the company’s consumption. But information has
> leaked out, sometimes through legal battles with local utilities and
> conservation groups…The conservation league called out the DHEC for giving
> Google so much water while asking a local public utility, Mount Pleasant
> Waterworks, to reduce its withdrawal from the aquifer by 57% over the next
> four years. The utility exceeded its previous peak use demand by 25% in May
> 2019, one of the driest months last year in Berkeley County, according to Clay
> Duffie, general manager of Mount Pleasant Waterworks
>
> <cite>[Sattiraju,
> 2020](https://www.bloomberg.com/news/features/2020-04-01/how-much-water-do-google-data-centers-use-billions-of-gallons).</cite>

### Amazon’s water usage

Amazon is the worst environmental performer of the big three. It plans to be
carbon neutral by 2040 and only matched 50% of its energy with purchases of
renewables in 2018, aiming for 100% by 2030 ([Amazon,
2019](https://press.aboutamazon.com/news-releases/news-release-details/amazon-co-founds-climate-pledge-setting-goal-meet-paris)).

Unlike Google and Microsoft, it has a huge logistics business which it
includes [in vague carbon footprint
figures](https://sustainability.aboutamazon.com/carbon-footprint). However, it
is not transparent submitting [no CDP
reports](https://www.cdp.net/en/responses?utf8=%E2%9C%93&queries%5Bname%5D=amazon&filters%5Byears%5D%5B%5D=2010&filters%5Byears%5D%5B%5D=2011&filters%5Byears%5D%5B%5D=2012&filters%5Byears%5D%5B%5D=2013&filters%5Byears%5D%5B%5D=2014&filters%5Byears%5D%5B%5D=2015&filters%5Byears%5D%5B%5D=2016&filters%5Byears%5D%5B%5D=2017&filters%5Byears%5D%5B%5D=2018&filters%5Byears%5D%5B%5D=2019&filters%5Byears%5D%5B%5D=2020) and
publishing no AWS cloud specific figures for its environmental footprint. Amazon
does have [a short page about water
usage](https://sustainability.aboutamazon.com/sustainability-in-the-cloud/reducing-water-used-for-cooling-in-aws-data-centers) but
it only describes in generalities and publishes no metrics.

### Do data centers use a lot of water?

Billions of litres sounds like a lot of water, but it depends what you compare
it to.

For example, total water usage in the US in 2015 was 446 billion litres *per
day* for irrigation, 88.2 billion gallons *per day* for domestic usage, and 15
billion gallons *per day* for mining ([Dieter et al,
2015](https://doi.org/10.3133/cir1441)). These are massive daily quantities for
quite large sectors. Compared to the 626 billion litres of water used by US data
centers in the whole of 2014 ([Shehabi et al,
2016](https://eta.lbl.gov/publications/united-states-data-center-energy)), this
is a very small proportion of overall water consumption.

Comparing these figures to other buildings allows them to be put into
perspective.

![Comparing data centers to other buildings](water-comparison.jpg "Comparing
data center water usage ([FitzGerald,
2015](https://www.wsj.com/articles/SB10007111583511843695404581067903126039290)).")

## Alternative water sources

Despite Amazon’s poor environmental efforts in comparison to Google and
Microsoft, it does make use of recycled water:

> AWS is expanding its use of non-potable water for cooling purposes to help
> conserve local drinking water sources. In Northern Virginia, AWS was the first
> data center operator to be approved to use recycled water with direct
> evaporative cooling technology. We partnered with Loudoun Water to demonstrate
> the benefits of recycled water for industrial cooling applications, and shared
> our operational best practices for utilizing recycled water in our data
> centers. In the AWS U.S. West (Oregon) Region, we have partnered with a local
> utility to use non-potable water for multiple data centers, and we are
> retrofitting AWS data centers in Northern California to use recycled water.
>
> <cite>[Amazon, 2020.](https://sustainability.aboutamazon.com/sustainability-in-the-cloud/reducing-water-used-for-cooling-in-aws-data-centers)</cite>

This is important to avoid depleting sources better used for other purposes.
Data centers are able to use water from any source but most come from municipal
sources such as reservoirs ([Heslin,
2016](https://journal.uptimeinstitute.com/dont-ignore-water-consumption/)). The
main reason for using these municipal sources is the reliability.

> Other sources of water include rainfall, gray water, and surface water. Very
> few data centers use these sources for a variety of reasons. Because rainfall
> can be unpredictable, for instance, it is mostly collected and used as a
> secondary or supplemental water supply. Similarly only a handful of data
> centers around the world are sited near lakes, rivers, or the ocean, but those
> data center operators could pump water from these sources through a heat
> exchanger. Data centers also sometimes use a body of water for an emergency
> water source for cooling towers or evaporative cooling systems. Finally, gray
> water, which is partially treated wastewater, can be utilized as a non-potable
> water source for irrigation or cooling tower use. These water sources are
> interdependent and may be short in supply during a sustained regional drought
>
> <cite>[Heslin,
> 2016](https://journal.uptimeinstitute.com/dont-ignore-water-consumption/).</cite>

![Diagram of the global hydrological cycle in the
Anthropocene](hydrological-cycle.png "Diagram of the global hydrological cycle
in the Anthropocene. Water fluxes expressed in 10^3 km^3 yr^–1). Uncertainty
represents the range of recent estimates expressed in %. Total human water use
(~24 10^3 km^3 yr^–1) is separated into green (soil moisture used by human crops
and rangelands, green arrow); blue (consumptive water use by agriculture,
industry and domestic activity, blue arrow); and grey (water necessary to dilute
human pollutants, which is represented with pink shading, red arrow). This
averaged depiction of the hydrological cycle does not represent important
seasonal and interannual variation in many pools and fluxes ([UN,
2020](https://unesdoc.unesco.org/ark:/48223/pf0000372985.locale=en)).")

Taking water from the sea is a potential option, but the salt-water can cause
problems with equipment. One idea is to co-locate data centers and desalination
facilities, both energy intensity operations.

> Deep Water Desal proposes to mitigate the power consumption of desalination in
> a very creative way. Rather than reduce the power required to desalinate
> water, they proposed to co-locate up to 150MW of data center facilities on
> site and reduce the power required to cool the data center. Essentially the
> desalination plant and data centers would be symbiotic and the overall power
> consumption of the combination of the two plants together would be lower.
>
> <cite>[Hamilton, 2014.](https://perspectives.mvdirona.com/2014/08/data-center-cooling-done-differently/)</cite>

Other companies are working with local utilities to make use of their
wastewater.

> At its 18 Bay Area data centers, Digital Realty Trust Inc., which runs several
> dozen centers around the world, has set an internal goal to eventually cut its
> water use by a quarter. The company struck deals with local utilities to use
> recycled wastewater where available, but that “gray water” isn’t always
> available. In Los Angeles, for instance, a new recycled water pipeline could
> take years to reach most of the region’s downtown data centers
>
> <cite>[FitzGerald, 2015.](https://www.wsj.com/articles/SB10007111583511843695404581067903126039290)</cite>

### Reducing water usage increases energy usage?

A full lifecycle analysis must be considered when evaluating alternatives.
Reducing absolute water consumption may increase the environmental footprint if
more energy is required. Water treatment involves energy intensive filtration
equipment and chemicals.

The WUEsource metric takes these external factors into account. It is defined as
(annual source energy water usage + annual site water usage) divided by IT
equipment energy ([The Green Grid,
2011](https://www.thegreengrid.org/en/resources/library-and-tools/238-Water-Usage-Effectiveness-%28WUE%29%3A-A-Green-Grid-Data-Center-Sustainability-Metric-)).

## Edge locations

Choosing the optimum data center location involves many tradeoffs. Hyperscale
data centers are often in regions with abundant access to renewable energy, such
as Google’s Finland data center ([Google,
2018](https://storage.googleapis.com/gweb-sustainability.appspot.com/pdf/24x7-carbon-free-energy-data-centers.pdf)).
However, these locations tend to be away from population centers which means
higher network response times as data must travel further to the end-user. As
urbanisation increases, the need for low latency will require data centers to be
sited closer to the user ([Kass and Ravagni, 2019](https://www.sdg-dc.com/)) but
these locations may be less suitable for access to renewable sources of
electricity or natural water sources for cooling.

Google has taken its DeepMind AI expertise to reduce cooling costs by up to 40%
([Evans and Gao,
2016](https://deepmind.com/blog/article/deepmind-ai-reduces-google-data-centre-cooling-bill-40); [Gao,
2017](https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/42542.pdf)).
Using data to extract efficiency improvements from existing infrastructure shows
there are still gains to be made without significant capital expenditure.

Microsoft have experimented with underwater data centers through [Project
Natick](https://natick.research.microsoft.com/), which avoids the need for
cooling due to the sea temperature.

> Project Natick is focused on a cloud future that can help better serve
> customers in areas which are near large bodies of water (where nearly 50% of
> society resides). The vision of operating containerized datacenters offshore
> near major population centers anticipates a highly interactive future
> requiring data resources located close to users. Deepwater deployment offers
> ready access to cooling and a controlled environment, and has the potential to
> be powered by co-located renewable power sources.

Where submerging servers isn’t possible, alternative cooling methods may be
viable. For example, in Jan 2020, [Mark Russinovich, Azure CTO, also
presented](https://youtu.be/X-0V6bYfTpA?t=1390) some tests Microsoft has been
conducting around liquid cooling for its servers.

![Slide from a presentation by Mark Russinovich](azure-liquid-cooling.png "Slide from a presentation by [Mark
Russinovich](https://youtu.be/X-0V6bYfTpA?t=1390) (2020).")

## Conclusions

Not enough attention is paid to water usage. In the developed world, we are too
used to turning the tap and having instant access to clean water for minimal
cost. Yet, there are still over 785 million people without access to simple
drinking water ([UN, 2019](https://undocs.org/E/2019/68)). With the added
pressure of risk to water due to climate change, even small savings in water
usage can have a major impact.

> A saving of 1% per year by better energy use or efficiency could provide water
> for 219 million people based on 50 L/day, depending on location and other
> factors.
>
> <cite>[UN,
> 2020](https://unesdoc.unesco.org/ark:/48223/pf0000372985.locale=en).</cite>

In this context, we pay too little attention to the efficiency of data center
water consumption. Cooling is not the largest consumer of data center power, and
is therefore only a small % of total cost, especially in the hyperscale cloud
environments ([Bullard,
2019](https://www.bloomberg.com/opinion/articles/2019-12-13/energy-efficiency-a-hot-problem-for-big-tech-data-centers)).

![Server power consumption by component](power-consumption-1.png "Server power
consumption by component, % of total by data center type
(visualisation: [Bullard,
2019](https://www.bloomberg.com/opinion/articles/2019-12-13/energy-efficiency-a-hot-problem-for-big-tech-data-centers);
data: [Shehabi et al,
2016](https://eta.lbl.gov/publications/united-states-data-center-energy))")

As usual with the data center industry, there is [insufficient
transparency](https://davidmytton.blog/sustainability-doesnt-work-without-transparency/).
Microsoft sets the standard but even they are only reporting absolute numbers.
There is no way to understand how efficient their operations are. The largest
cloud provider, Amazon, doesn’t publish anything. Facebook is a leading example
but they do not sell their infrastructure capacity so 3rd parties are unable to
take advantage of their efficiency.

That said, it is clear that moving to the cloud helps significantly. [Cloud data
centers are more
efficient](https://davidmytton.blog/data-center-energy-and-the-importance-of-efficiency/),
the big three providers [procure the most renewable
energy](https://davidmytton.blog/how-can-data-centers-use-100-renewable-electricity/),
offer the most [environmentally aware
products](https://davidmytton.blog/energy-efficiency-edge-compute-and-serverless/),
and they all continue to invest in improving their environmental sustainability.
They operate at such a scale which allows them to justify experimental projects
like submersible data centers. All their customers benefit from the efficiency
improvements.

Just as customers are [starting to ask cloud vendors for data about their carbon
footprint](https://davidmytton.blog/shifting-the-sustainability-focus-from-the-individual-to-the-corporation/),
they should also include water consumption in their evaluation criteria. Cloud
providers should talk as much about how they are reducing water usage through
monitoring their WUEsource ratio as they do about reducing carbon emissions and
monitoring their PUE ratio. However, until there is pressure from the market to
select based on a full range of environmental standards, things are unlikely to
change.
