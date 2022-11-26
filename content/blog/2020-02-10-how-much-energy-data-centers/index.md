---
title: "How much energy do data centers use?"
date: 2020-02-10
modified: 2022-11-26
draft: false
tags: ["Data Center Energy", "IT Energy", "Cloud", "Energy Efficiency"]
summary: "Globally, data centers were estimated to use between 196 terawatt 
hours (TWh) and 400 TWh in 2020, or between 1-2% of global electricity demand."
url: how-much-energy-do-data-centers-use
---

Globally, data centers were estimated to use between 196 terawatt hours (TWh)
([Masanet et al, 2020](https://doi.org/10.1126/science.aba3758)) and 400 TWh
([Hintemann, 2020](https://dx.doi.org/10.13140/RG.2.2.26033.40800)) in 2020.
This would mean data centers consume between 1-2% of global electricity demand.
An upcoming publication [mentioned in a brief research
note](https://rgdoi.net/10.13140/RG.2.2.31826.43207) from Borderstep may put the
estimate at 350-500 TWh in 2021.

In Aug 2022 I co-authored [a comprehensive review of all data center energy
estimates](https://doi.org/10.1016/j.joule.2022.07.011) between 2007-2021. In
the review we analyze 258 data center energy estimates from 46 original
publications between 2007 and 2021 to assess their reliability by examining the
676 sources used. From this group, the only credible global models are from the
two research groups represented by Masanet and Hintemann (Borderstep).

However, there are other local publications which are worth examining because
they suggest that the estimates could be much higher. For example, [Avgerinou,
Bertoldi & Castellazzi L, 2017](https://doi.org/10.3390/en10101470) estimated
that 104 TWh will be used by European Union data centers in 2020, which makes a
global total of 200 TWh on the low end. This can be contrasted with a more
recent analysis by [Montevecchi et al](https://dx.doi.org/10.2759/3320) which
suggestes a major increase in the energy consumption of data centers in the
EU28: 53.9 TWh/a to 76.8 TWh/a between 2010 and 2018. This is expected to grow
21% to 92.6 TWh/a by 2025.
[Note](/paper-notes-energy-efficient-cloud-computing-technologies-and-policies-for-an-eco-friendly-cloud-market/)
that this is based on the Hintemann/Borderstep model, so it is not entirely
independent.

The variance in estimates is a major challenge for anyone trying to get to the
bottom of how much energy data centers use. In [the Joule
review](https://doi.org/10.1016/j.joule.2022.07.011) we show that 31% of sources
were from peer-reviewed publications, 38% were from non-peer-reviewed reports,
and many lacked clear methodologies and data provenance. We also highlight
issues with source availability—there is a reliance on private data from IDC
(43%) and Cisco (30%), 11% of sources had broken web links, and 10% were cited
with insufficient detail to locate.

In this article, I’ll look at what a data center is, the major components that
make up a data center, their energy consumption and the relevancy of cloud
computing and energy efficiency improvements.

## What is a data center?

In the same way applications run on your laptop, accessing anything on the
internet also requires those applications to run on a computer. These computers
are called servers. They are just like a laptop but do not have a screen or
keyboard and must be located somewhere where they have access to the internet,
power, and cooling. Such places are called data centers. These facilities can
range in size from small 100ft2 cabinets up to massive 400,000ft2 “hyperscale”
warehouses ([Shehabi et al,
2016](https://eta.lbl.gov/publications/united-states-data-center-energy)).
Whenever you use any service on the internet, you are connecting to one of many
millions of servers located in one of many thousands of data centers around the
world.

## Servers

Having grown from around 11 million in 2006, as of 2020 there are an estimated
18 million servers deployed in data centers globally ([Shehabi et al,
2016](https://eta.lbl.gov/publications/united-states-data-center-energy)). Power
drawn is partially related to usage, expressed as a percentage of maximum power.
This is related to the number of Central Processing Unit (CPU) sockets and has
remained static since 2007: 118W for single socket servers and 365W for two
socket servers ([Shehabi et al,
2016](https://eta.lbl.gov/publications/united-states-data-center-energy); [Shehabi
et al, 2018](https://doi.org/10.1088/1748-9326/aaec9c)).

Power proportionality is key to understanding the efficiency of servers. This
scales in proportion to utilisation. With perfect power proportionality, a
server at 10% utilisation will draw 10% of its maximum power ([Shehabi et al,
2016](https://eta.lbl.gov/publications/united-states-data-center-energy)). This
is measured as Dynamic Range – a ratio between idle power and maximum power
which can be affected by hardware properties, power management software and the
server configuration ([Shehabi et al,
2016](https://eta.lbl.gov/publications/united-states-data-center-energy)).

![Dynamic range of 1- and 2-socket servers](server-dynamic-range-1.png "Dynamic
range of 1- and 2-socket servers ([Shehabi et al,
2016](https://eta.lbl.gov/publications/united-states-data-center-energy)).")

These improvements in server dynamic range have been coupled with improvements
in utilisation caused by software management systems and the move to hyperscale
facilities run by the cloud providers. However, despite this most servers still
rarely run at full utilisation – the most efficient run at only 50% ([Masanet et
al,
2013](https://eta.lbl.gov/publications/energy-efficiency-potential-cloud); [Shehabi
et al,
2016](https://eta.lbl.gov/publications/united-states-data-center-energy)). This
translates to 40,000 GWh/yr in direct server electricity consumption in the US
as of 2020, of which half can be wasted by idle servers ([Shehabi et al,
2016](https://eta.lbl.gov/publications/united-states-data-center-energy)).

## Storage

The amount of data generated by humanity is growing every year ([Statista,
2018](https://www.statista.com/statistics/871513/worldwide-data-created/)), and
it needs to be stored on disks. Power drawn per disk varies by drive type. Hard
Disk Drive (HDD) wattage is not related to capacity and was estimated at
14W/disk in 2006, decreasing by 5% each year to 8.6W/disk in 2015 ([Shehabi et
al, 2016](https://eta.lbl.gov/publications/united-states-data-center-energy)).
Solid State Disk (SSD) wattage has remained a constant 6W/disk since 2010 but
the wattage per terabyte (TB) has been improving, with capacity per watt
increasing 3-4x between 2010-2020 ([Shehabi et al,
2016](https://eta.lbl.gov/publications/united-states-data-center-energy)).

![Average wattage of storage drives in US data centres](average-disk-wattage.png "Average wattage of storage drives in US data centers ([Shehabi et al,
2016](https://eta.lbl.gov/publications/united-states-data-center-energy)).")

Total electricity usage for disks in the US in 2020 is estimated at just over
8,000 GWh/yr across a total of 1,000 million TB of storage ([Shehabi et al,
2016](https://eta.lbl.gov/publications/united-states-data-center-energy)). With
an estimated lifespan of 4.4 years, number of disks deployed is plateauing, but
total capacity is in-creasing ([Shehabi et al,
2016](https://eta.lbl.gov/publications/united-states-data-center-energy)).

## Network

Servers need to be connected to each other, and to the internet; this is the
network component. Network devices use power related to the number of ports and
their speed ([Shehabi et al,
2016](https://eta.lbl.gov/publications/united-states-data-center-energy)).

![Assumed network power for four port speeds](average-network-power.png "Assumed
network power for four port speeds ([Shehabi,
2016](https://eta.lbl.gov/publications/united-states-data-center-energy)).")

Wildly varying estimates for the energy intensity of the internet have been
published, ranging from 136 kWh/GB in 2000 to 0.004 kWh/GB in 2008, but a more
recent estimate analysing calculation methodologies settled on 0.06 kWh/GB for
2015 ([Aslan et al, 2018](https://doi.org/10.1111/jiec.12630)). This is
decreasing by 50% every 2 years ([Aslan et al,
2018](https://doi.org/10.1111/jiec.12630)).

Calculating the energy intensity of the internet is difficult – [Aslan et al
(2018)](https://doi.org/10.1111/jiec.12630) only considers fixed line networks
in developed countries. Calculations are missing for mobile networks that will
account over 20% of all internet traffic by 2022, growing at 46% per year
([Cisco,
2019](https://www.cisco.com/c/en/us/solutions/collateral/service-provider/visual-networking-index-vni/white-paper-c11-741490.pdf));
and internal connectivity within data centers is not included but is doubling
every 12-15 months ([Singh et al,
2015](https://doi.org/10.1145/2785956.2787508)). These excluded factors and no
recent calculations examining networking equipment speeds up to current fastest
400Gb ([Ethernet Alliance,
2019](https://ethernetalliance.org/technology/2019-roadmap/)) devices means that
it is difficult to estimate the true energy impact of networking today.

## Infrastructure

The data center building consists of infrastructure to support the servers,
disks and networking equipment it contains. This includes cooling, power
distribution, backup batteries and generators, lighting, fire suppression, and
the building materials themselves ([GHG Protocol,
2017](https://ghgprotocol.org/sites/default/files/GHGP-ICTSG%20-%20ALL%20Chapters.pdf)).
The infrastructure overhead is measured using Power Usage Effectiveness (PUE)
([Uptime Institute,
2019](https://uptimeinstitute.com/resources/asset/2019-data-center-industry-survey)).
This is the ratio between power drawn by the infrastructure components and power
delivered to the servers, disks and networking equipment ([GHG Protocol,
2017](https://ghgprotocol.org/sites/default/files/GHGP-ICTSG%20-%20ALL%20Chapters.pdf)).

A PUE of 1.0 means 100% of data center power inputs go to the IT equipment. The
industry average PUE is 1.67 ([Uptime Institute,
2019](https://uptimeinstitute.com/resources/asset/2019-data-center-industry-survey))
but ranges from 1.11 to 3.0 ([Google,
2019](https://services.google.com/fh/files/misc/google_2019-environmental-report.pdf); [Shehabi
et al,
2016](https://eta.lbl.gov/publications/united-states-data-center-energy)).

Using the PUE ratio alone has been criticised because it will decrease when IT
load increases ([Brady et al,
2013](https://doi.org/10.1016/j.enconman.2013.07.035)) even though efficiency
may not have improved. This makes it useful to compare facilities rather than
indicating efficiency by itself. Although out of scope for this briefing, data
centers have environmental impacts wider than just energy: water used for
cooling and the life cycle of IT equipment are other important factors not
included in PUE ([GHG Protocol,
2017](https://ghgprotocol.org/sites/default/files/GHGP-ICTSG%20-%20ALL%20Chapters.pdf)).
Metrics such as Water Use Effectiveness and Land Use Effectiveness, alongside
Life Cycle Analysis, have been suggested to help understand true impacts ([Kass
and Ravagni, 2019](https://www.sdg-dc.com/)).

In a traditional data center, the fuel to server efficiency is only 17.5% – this
is due the generally low efficiency of generating electricity through fossil
fuels (which still make up the majority of the energy mix in most power grids)
combined with the grid losses and the with losses in the power distribution
systems within the data center ([Zhao et al,
2014](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/FCDC-TechReport.pdf)).
Fuel cells have been investigated as a method of eliminating these losses ([Zhao
et al,
2014](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/FCDC-TechReport.pdf))
and could increase efficiency to 29.5%.

![Data center efficiency diagram](data-centre-fuel-cell-efficiency.png "A)
Traditional, data center system losses and B) fuel cell powered data center
system losses ([Zhao et al,
2014](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/FCDC-TechReport.pdf)).")

With further modifications to data center design to use Direct Current (DC) from
the fuel cell and bypassing the Uninterruptible Power Supply (used for backup
power but not needed with gas reliability at 99.999%), 53.2% efficiency could be
achieved ([Zhao et al,
2014](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/FCDC-TechReport.pdf)).

![Efficiency diagram of DC configuration with UPS](dc-efficiency-with-ups.png "Efficiency diagram of DC configuration with UPS ([Zhao et al,
2014](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/FCDC-TechReport.pdf))")

![Efficiency diagram of DC configuration without
UPS](dc-efficiency-without-ups.png "Efficiency diagram of DC configuration
without UPS ([Zhao et al,
2014](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/FCDC-TechReport.pdf)).")

## Cloud computing

Physical IT equipment can be measured to determine the environmental impact in
embodied energy as well as power drawn during actual usage. This can then be
combined with calculations from the data center components to calculate
emissions. Indeed, these calculations are part of the Greenhouse Gas Protocol
([GHG Protocol,
2017](https://ghgprotocol.org/sites/default/files/GHGP-ICTSG%20-%20ALL%20Chapters.pdf))
and standards exist for constructing energy efficient data centers ([Huusko et
al, 2012](https://doi.org/10.1007/978-3-642-33645-4)). These types of emissions
fall under the Scope 1 and Scope 2 reporting guidelines ([GHG Protocol,
2015](https://ghgprotocol.org/corporate-standard)) that many organisations are
required to publish ([Department for Business, Energy & Industrial Strategy,
2018](https://www.gov.uk/government/consultations/streamlined-energy-and-carbon-reporting)).

However, when IT workloads are moved to the cloud and resources are purchased in
tiny “virtual” units on a pay-as-you-go basis, their associated emissions shift
to voluntary Scope 3 reporting as “indirect” or outsourced emissions ([Mytton,
2020a](https://doi.org/10.1038/s41558-020-0837-6)). This means that cloud
customers must rely on the cloud provider to release enough data to calculate
their emissions. The major cloud vendors (Amazon Web Services, Google Cloud and
Microsoft Azure) publish aggregated global data, and with varying degrees of
transparency ([Mytton, 2020b](https://doi.org/10.1186/s13677-020-00185-8)).

Amazon is the least transparent – they report limited environmental data other
than their 2018 total carbon footprint: 44.4 million tCO2e ([Amazon,
2020](https://sustainability.aboutamazon.com/carbon-footprint)). Since this
includes all of Amazon’s operations and is not broken out for the Amazon Web
Services cloud business, this is not a useful figure. This lack of transparency
resulted in Amazon being criticised in a Greenpeace report ([Cook, Jardim and
Craighill, 2019](https://www.greenpeace.org/usa/reports/click-clean-virginia/)).

With 53% of servers expected to be in hyperscale facilities by 2021 ([Cisco,
2018](https://www.cisco.com/c/en/us/solutions/collateral/service-provider/global-cloud-index-gci/white-paper-c11-738085.html))
and the cloud computing market growing from $6bn in 2008 to $288bn in 2019
([Forrester,
2019](https://www.tatacommunications.com/wp-content/uploads/2019/02/Forrester-Report.pdf)),
it is important that cloud vendors are transparent about their environmental
footprint.

As of 2022, [all three cloud operators give their customers cloud carbon
calculators](/cloud-emissions-transparency-stage-1-completed-what-next/),
although Microsoft’s is only available if you have an Enterprise Azure contract.
How these figures are calculated is a separate
question. [Google](https://cloud.google.com/carbon-footprint/docs/methodology) and [Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=56950) provide
details about their methodology, but AWS does not. [AWS also uses market-based
GHG Protocol
calculations](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/ccft-estimation.html) whereas
Google uses location-based reporting. Location-based is more useful because [it
considers where the electricity is
consumed](https://ghgprotocol.org/blog/top-ten-questions-about-scope-2-guidance) in
relation to carbon mitigation in that region e.g. renewables on the same grid as
the data center. It’s generally accepted practice to report both, but
location-based reporting is important for encouraging demand for more clean
energy where it is actually consumed.

![Total US electricity consumption by data centre
type](data-center-electricity-consumption.png "Total US electricity consumption
by data center type ([Shehabi,
2016](https://eta.lbl.gov/publications/united-states-data-center-energy)).")

Hyperscale providers operate at such a scale that they can justify activities
such as Google building their own servers ([Metz,
2016](https://www.wired.com/2016/05/googles-making-chips-now-time-intel-freak/); [GCP,
2017](https://cloud.google.com/security/infrastructure/design/#hardware_design_and_provenance))
and Microsoft constructing the first ever gas data center ([Belady & James,
2017](https://blogs.microsoft.com/green/2017/09/24/redesigning-datacenters-advanced-energy-future/)),
all of which contribute to improving energy efficiency. The technology sector is
also the largest purchaser of renewables ([Kamiya, and Kvarnström,
2019](https://www.iea.org/commentaries/data-centres-and-energy-from-global-headlines-to-local-headaches))
([but what does 100% renewable actually
mean?](https://davidmytton.blog/how-can-data-centers-use-100-renewable-electricity/)).

## Efficiency challenges ahead?

Although the last 20 years have seen major efficiency improvements, predictions
suggest these may be coming to an end. As a result of market growth and
diminishing returns from existing approaches to efficiency improvements there is
a suggestion that data center energy usage will double by 2030. If electricity
continues to be a major source of data center energy and is generated from
non-renewable sources, data center emissions could exceed the aviation industry
which is currently responsible for 2% of annual human-generated CO2 ([IATA,
2020](https://www.iata.org/en/policy/environment/climate-change/)).

![Current trends of US data centre equipment use from
2000-2020](data-center-electricity-trends.png "Current trends of US data center
equipment use from 2000-2020 (historical and projected), with two alternative
scenarios beginning in 2010 ([Shehabi et al,
2018](https://doi.org/10.1088/1748-9326/aaec9c)).")

Data center energy projections have been wrong in the past ([Malmodin and
Lundén, 2018](https://doi.org/10.3390/su10093027); [Jones,
2018](https://doi.org/10.1038/d41586-018-06610-y); [Masanet et al,
2019](https://doi.org/10.1038/s41558-019-0535-4)) and improvements such as fuel
cell powered data centers are promising. However, several scenarios could
combine to hamper future improvements:

- Moore’s Law states that CPU performance per watt doubles every 1.5 years
  ([Bashroush, 2018](https://doi.org/10.1109/TSUSC.2018.2795465)). If data
  center hardware continues to only be refreshed every 4.4 years, then major
  efficiency improvements may be missed ([Bashroush,
  2018](https://doi.org/10.1109/TSUSC.2018.2795465)). This also assumes that
  Moore’s Law will continue, which is uncertain ([Huang,
  2015](https://spectrum.ieee.org/semiconductors/design/the-death-of-moores-law-will-spur-innovation)).
  Can we overcome the physical limits of ever-smaller chips? If replacement
  cycles become more frequent, how will that affect other environmental metrics
  such as embodied energy and waste?
- The introduction of new types of chips for specialist applications e.g.
  Graphics Processing Units (GPUs) for machine learning, could draw more power
  with unknown efficiency profiles ([Shehabi et al,
  2018](https://doi.org/10.1088/1748-9326/aaec9c)). What efficiency profile will
  these chips have, and will we see historically similar performance per-watt
  improvements?
- Hyperscale data centers are often in regions with abundant access to renewable
  energy, such as Google’s Finland data center ([Google,
  2018](https://storage.googleapis.com/gweb-sustainability.appspot.com/pdf/24x7-carbon-free-energy-data-centers.pdf)).
  However, these locations tend to be away from population centers which means
  higher network response times as data must travel further to the end-user. As
  urbanisation increases, the need for low latency will require data centers to
  be sited closer to the user ([Kass and Ravagni,
  2019](https://www.sdg-dc.com/)) but these locations may be less suitable for
  access to renewable sources of electricity or natural water sources for
  cooling. Can this be mitigated by gas fuel cells?

## Conclusions

Data center energy usage is significant but historical efficiency improvements
mean that growth has decoupled from energy consumption. Trends such as the cloud
allow efficiency improvements to take place at huge scale but there are problems
on the horizon. Approaching the physical limits of Moore’s Law and new
technologies such as machine learning mean historical improvements cannot be
assumed. The data center industry is changing rapidly and how that will affect
energy profiles is uncertain.
