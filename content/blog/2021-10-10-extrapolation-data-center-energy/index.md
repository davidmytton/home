---
title: "Extrapolation of data center energy estimates"
date: 2021-10-10
modified: 2021-10-10
draft: false
tags: ["Data Center Energy", "Transparency"]
summary: "There are currently only two credible estimates for global data 
center energy consumption: 196 TWh to 400 TWh for 2020. Why do we see vastly 
higher reports?"
url: extrapolation-of-data-center-energy-estimates
---

There are currently only two credible [estimates for global data center energy
consumption](https://davidmytton.blog/how-much-energy-do-data-centers-use/).
These range from 196 TWh ([Masanet et al.,
2020](https://doi.org/10.1126/science.aba3758)) to 400 TWh ([Hintemann,
2020](https://www.researchgate.net/publication/341431606_Data_centers_2018_Efficiency_gains_are_not_enough_Data_center_energy_consumption_continues_to_rise_significantly_-_Cloud_computing_boosts_growth))
for 2020. Both papers are updated estimates from many years of related
publications (from the same authors) which primarily use bottom-up calculations
based on low-level hardware energy consumption and shipment statistics to
provide estimated models. The difference mainly comes down to the system
boundaries as to whether cryptocurrency mining is included, and the extent of
workload migration from old data centers to the cloud.

These figures offer a rough figure of 1-2% of total global electricity demand
coming from data centers. Although we can make some hand-waving estimates about
what that means for carbon footprint, to get anywhere near an acceptable level
of accuracy would require at least regional- and ideally country-level energy
stats and carbon emissions factors. Even countries as close together as the UK
and France have very different grid mixes which would affect the total carbon
footprint of data centers operating in those countries.

Over the last decade, IT has seen massive growth in usage. More people are using
more IT services. IP traffic has grown almost x20 over that period. But
technology has also been improving. Computers, servers and network equipment are
more efficient, so the growth in usage has decoupled from the energy
consumption.

That isn’t reflected in the common narrative around data center energy because
there are several different methodologies for assessing IT energy, and most of
them require nuance to understand. The mainstream media is not good at nuance,
so the easiest is to take values for a given year and apply historical growth
rates, maybe with an adjustment for “efficiency”. This extrapolation-based
approach works fine in some situations, but those need to be situations with
very few variables that affect the growth. IT is not one of them.

![XKCD cartoon](xkcd-extrapolating.png "[xkcd](https://xkcd.com/605/):
Extrapolating.")

Energy efficiency improvements are just one variable. Processors are more
powerful. Infrastructure is moving to the cloud. Hyperscale data centers have
become very efficient. More renewable energy is being deployed for data centers.
All these impact energy estimates, and are very difficult to accurately estimate
when using extrapolation based methodologies.

Extrapolation methodologies have their place – they can be useful for creating
simple scenarios to help make broad decisions – but they are more often used to
back up a predetermined narrative. The situation is actually more nuanced than
meets the eye.

This is a problem for the mainstream narrative that wants to make a simple case
that data centers are using loads of energy, emitting lots of carbon, and are
bad for the planet.

You will often see discussions of the vast amount of energy consumed by data
centers emitting lots of carbon and damaging the planet. These tend to be used
by the mainstream media, lobby groups urging “digital sobriety” or case studies
showing how much a particular technology or product has “saved” the planet. Most
of these stem from extrapolation based models, the most commonly cited of which
is [Andrae, A.S.G. & Edler, T. (2015)](https://www.mdpi.com/2078-1547/6/1/117).

Whenever you see crazy data center and/or IT energy estimates, you can bet the
numbers are based on Andrae and Edler (2015), or one of the followup papers.
These use simplistic extrapolation methodologies to arrive at absurd numbers,
not least because they attempt to estimate the very broad category of “IT”
(which also includes data centers). But as it reaches 600 citations, the bad
estimates continue to be referenced. It’s a great example of the idea that you
can find academic papers to back up any point you want.

To illustrate, the historical estimates of past papers can be plotted against
the actual values produced using retrospective modelling once the real data
becomes available:

![Graphs of comparison analysis](comparison-analysis-methods.png "Comparison of
forward‐looking analysis methods. (a) Global data center IP traffic. (b)
Comparison of forward‐looking analysis methods. Sources
[4](https://doi.org/10.1126/science.aba3758),
[11](https://doi.org/10.1016/j.jclepro.2017.12.239), 12 – Andrae ASG. Total
consumer power consumption forecast. Presented at the Nordic Digital Business
Summit; october 2017, [13](https://www.mdpi.com/2078-1547/6/1/117),
[18](https://www.researchgate.net/profile/Anders-Andrae/publication/255923829_Emerging_Trends_in_Electricity_Consumption_for_Consumer_ICT/links/00b7d520df6b552e5f000000Emerging-Trends-in-Electricity-Consumption-for-Consumer-ICT.pdf). **From:** Lei,
N. & Masanet, E.R. (2021) Global Data Center Energy Demand and Strategies to
Conserve Energy. In: Hwaiyu Geng (ed.). _Data Center Handbook: Plan, Design,
Build, and Operations of a Smart Data Center_. John Wiley & Sons, Inc. p.
Available from: <https://doi.org/10.1002/9781119597537.ch2>")

That’s not to say that the 196-400 TWh range is infallible. Indeed, a survey
methodology by the European Union estimated 104 TWh of data center energy
consumption just within EU countries in 2020 ([Avgerinou, Bertoldi & Castellazzi
L, 2017](https://doi.org/10.3390/en10101470)). That puts a global figure of 196
on the low end. The point is that finding a number from a scientific article to
support your conclusions is not the end of the story.

Two of the leading researchers in this field [recently published a
good](https://doi.org/10.1016/j.joule.2021.05.007) (and short) guide to how to
avoid bad estimates of IT energy consumption:

1. Check the methodology of the paper you are citing. This can be difficult
   without a detailed understanding of the area, but common red-flags include
   the lack of a detailed, transparent method with original data and
   calculations. Even simpler than that – how old is the data? Estimates must
   specify the year they apply to because important factors like overall energy
   efficiency and emissions factors can change quite quickly. Historical
   estimates say something about the past, not necessarily the future.
2. Short term changes do not necessarily result in long term impacts. The
   increase in internet traffic due to working from home last year in the COVID
   lockdowns did not result in a proportional increase in energy consumption,
   as reported by several major telecoms companies. Energy proportionality is
   important to understand in the context of a specific timeframe. Systems can
   be designed with spare capacity for short term changes, but how do they
   adapt in the long run?
3. Projections more than a few years out are probably highly inaccurate. As
   discussed above, there are too many factors that mean future IT energy
   estimates are too difficult to predict more than a couple of years into the
   future. Moore’s Law operated on a ~2 year timeline, but [we’re now unsure
   how that might
   change](https://davidmytton.blog/paper-notes-what-will-drive-computer-performance-after-moores-law/).
4. IT systems are complex and the system must be considered as a whole, or the
   system you are comparing must match. Traditional data centers are very
   inefficient but hyperscale cloud data centers are very efficient. IT usage
   might have increased, but where are those workloads placed? Substitution
   effects can be unintuitive.

Of course it’s easy to blame the media for using figures to fit a narrative, but
the industry needs to do better as well. [The common theme I’ve found throughout
my
research](https://davidmytton.blog/sustainability-doesnt-work-without-transparency/) in
this area is the [lack of
transparency](https://davidmytton.blog/standardizing-carbon-accounting/).
Estimates are inaccurate because of insufficient data. If the industry wants to
avoid the bad PR of bad calculations, it needs to release more granular data.
