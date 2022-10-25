---
title: "Barriers for startups tackling data center energy consumption"
date: 2020-09-03
modified: 2020-09-03
draft: false
tags: ["Startups", "IT Energy", "Data Center Energy", "Energy Efficiency"]
summary: "There is scope to start something tackling the problem of data center 
energy consumption. However, there are significant challenges: how to measure 
the problem, the uncertainty around the current situation, and the limited 
number of growth buyers."
url: barriers-for-startups-tackling-data-center-energy-consumption
---

Recently I have spoken to several people asking about startups in data center
energy, the area of focus of [my MSc
research](https://davidmytton.blog/publications/) at Imperial College London.
The most common question is: “Where are the interesting opportunities?”,
followed by “What interesting startups have you seen tackling this?”

If you have an idea for a new software product, it is a rule that another
startup already exists doing the same thing, and they have probably raised
significant VC funding! The on-prem to SaaS transition has happened and
everything you can think of has multiple businesses already competing. Standing
out requires more thoughtful innovation, perhaps by vertical specialisation,
better UX, or [reimagining a “done”
product](https://davidmytton.blog/the-prosumer-software-commercial-go-to-market-approach/) with
a [strong opinion](https://davidmytton.blog/opinionated-software/).

Innovation in data centers, and energy consumption of IT, is different. There
are few companies tackling this and the startups I have seen to-date have not
been impressive. Why is this?

## How much energy do data centers use?

As I have written in the past:

> Estimates of annual data center electricity usage vary from 200 terawatt hours
> (TWh) ([Jones, 2018](https://doi.org/10.1038/d41586-018-06610-y)) to 500 TWh
> ([Bashroush & Lawrence,
> 2020](https://uptimeinstitute.com/beyond-pue-tackling-it%E2%80%99s-wasted-terawatts)).
> The lower of these figures would suggest that data centers consume 1% of
> global electricity ([Jones,
> 2018](https://doi.org/10.1038/d41586-018-06610-y)), but this could be
> significantly higher. One study suggests that global data center energy usage
> was 270 TWh in 2012 ([Van Heddeghem et al,
> 2014](https://doi.org/10.1016/j.comcom.2014.02.008)). Another study estimates
> that 104 TWh will be used by European Union data centers in 2020, which makes
> a global total of 200 TWh unlikely ([Avgerinou, Bertoldi & Castellazzi L,
> 2017](https://doi.org/10.3390/en10101470)).
>
> <cite>[How much energy do data centers
> use?](https://davidmytton.blog/how-much-energy-do-data-centers-use/) Mytton,
> 2020</cite>

This highlights the big issue of transparency. Not only do we not know how much
energy data centers consume, there are competing projections for whether data
center energy consumption is going to fall ([Masanet et al.,
2020](https://doi.org/10.1126/science.aba3758)), plateau ([Shehabi et al,
2018](https://doi.org/10.1088/1748-9326/aaec9c)) or grow ([Andrae and Edler,
2015](https://doi.org/10.3390/challe6010117)).

There are several complex factors which mean past trends may not play out the
same way in the future. The industry moves rapidly and trends such as low power
ARM chips are offset by the huge number of IoT devices coming online. Further,
new types of components such as ML specialised chips have unknown energy
profiles which need analysis ([García-Martín et al.,
2019](https://doi.org/10.1016/j.jpdc.2019.07.007)) with some estimates showing
that training complex models can generate more emissions than 300 flights from
San Francisco to New York ([Strubell, Ganesh & McCallum, 2019)](https://arxiv.org/abs/1906.02243).

Understanding the trajectory is crucial to whether we consider data center
energy consumption a problem or not. If data center energy consumption is
falling then it may not be a top priority. However, if it is true that 30% of
energy demand in Ireland will be from data centers in 2028 ([EirGrid,
2019](http://www.eirgridgroup.com/site-files/library/EirGrid/EirGrid-Group-All-Island-Generation-Capacity-Statement-2019-2028.pdf)),
and 15% in Denmark by 2030 ([Danish Energy Agency,
2019](https://ens.dk/sites/ens.dk/files/Analyser/deco19.pdf)), then this is a
serious issue that makes sense for startups to tackle.

## Who is the buyer?

- Who is the buyer of electricity and where does that appear on the P&L?
- Who is responsible for that cost?

If you are buying physical servers and racking them in a data center, you are
the buyer of electricity. You care about how much power servers consume in
aggregate, and at peak loads.

If you are renting dedicated servers as a product from a hosting vendor you are
paying a blended price of hardware, networking and support. That includes
electricity, but it is not broken out. The hosting vendor is the buyer and they
provision power for peak capacity. If the server has good power proportionality
and it is under-utilised then that will show up as as saving for the hosting
vendor, but the customer sees no benefit.

If you are buying cloud resources in the form of VMs (or other direct compute,
such as dedicated instances or containers), you are another level up the stack.
The cloud vendor is procuring the hardware which consumes electricity. The cloud
vendor customer has no visibility of the underlying electricity consumption
([Mytton, 2020](https://doi.org/10.1186/s13677-020-00185-8)) and any
efficiencies in the infrastructure accrue to the cloud vendor.

At the top of the infrastructure stack, if you are buying products like managed
databases or queues, you do not even see the underlying compute resources being
consumed. Energy efficiencies accrue to the hosting vendor.

Finally, if you are end-user of a SaaS product e.g. Gmail, you might be buying
nothing (as a free user), or are paying on a per seat basis e.g. for Microsoft 365. There is no correlation between price and resource consumption. Again, any
efficiencies accrue to the hosting vendor who sells resources to the SaaS vendor
(which may be the same company).

Note there is one place where energy efficiencies are noticed: if you own/rack
your own hardware, either as a hosting vendor, cloud vendor, or a business that
runs its own infrastructure.

## Where is the growth?

All trends point towards public cloud as the source of growth for infrastructure
spend. The colo market is not dead:

> The datacenter colocation market has now grown to $40B per year. Seems less
> and less likely that “on-premise” enterprise software will completely
> disappear as some had predicted.
>
> <cite>[Chetan Puttagunta](https://twitter.com/chetanp) via Twitter (2020)</cite>

But $40B/yr is small compared to the $288bn in cloud computing market 2019
([Forrester,
2019](https://www.tatacommunications.com/wp-content/uploads/2019/02/Forrester-Report.pdf)).

There are only 3 cloud computing companies that matter: Amazon, Google and
Microsoft. [Nobody else has the Capex to be a relevant
player](https://www.platformonomics.com/2020/07/follow-the-capex-clown-watch/).
They are all working on their own innovations in energy consumption, which makes
the sales process even harder because you have to compete with private, internal
projects.

## Challenging, but not impossible

Startups exist to find unusual opportunities and overcome structural challenges.
Data centers are just one of the two components which make up the majority of
the energy footprint of IT ([Jones,
2018](https://doi.org/10.1038/d41586-018-06610-y)). Networking is the second.
And given the expected growth of data volumes over the coming decade ([Cisco,
2020](https://www.cisco.com/c/en/us/solutions/collateral/executive-perspectives/annual-internet-report/white-paper-c11-741490.html)),
potentially a bigger opportunity than data centers e.g. 5G is initially expected
to consume x3 the energy of 4G networks ([Koziol,
2019](https://spectrum.ieee.org/telecom/wireless/5gs-waveform-is-a-battery-vampire)),
although the industry says this will fall to become x20 more efficient by 2030
([Orange,
2020](https://hellofuture.orange.com/en/5g-energy-efficiency-by-design/)).

There is scope to start something in this space and tackle the problem of data
center energy consumption. However, there are significant challenges: how to
measure the problem, the uncertainty around the current situation, and the
limited number of growth buyers, mean that this is a difficult area for startups
to tackle.
