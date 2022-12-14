---
title: "Energy systems and 24/7 carbon free energy"
date: 2022-11-07
modified: 2022-11-07
draft: false
tags: ["Data Center Energy", "Energy Systems"]
summary: "With the grid mix constantly changing, what needs to happen to energy 
systems to reach the goal of 24/7 carbon free energy? Google has funded two 
studies to find out."
canonicalUrl: https://www.devsustainability.com/p/energy-systems-and-247-carbon-free
url: energy-systems-and-24/7-carbon-free-energy
---

Claims of “100% renewable energy” are almost always greenwashing. The
electricity grid mix varies throughout the day which means most organizations
claiming to use only renewable energy are doing so [only on an accounting
basis](https://davidmytton.blog/how-can-data-centers-use-100-renewable-electricity/).

Using Renewable Energy Certificates (RECs) or Renewable Energy Guarantees of
Origin (REGOs) are common, but [they can’t credibly be
used](https://davidmytton.blog/recs-cannot-be-used-to-back-claims-of-100-renewable-energy/)
to back claims of 100% renewables. Power Purchase Agreements (PPAs) or green
supply agreements are much more complex, but do at least deliver on the claims.

However, if the focus is on “renewables” like solar and wind, then they are
still inherently variable. Even high quality products like direct PPAs can’t
make up for times when there is insufficient renewable energy available on the
grid.

This is why there is a push for what’s known as 24/7 carbon free energy. The
goal is that every unit of consumption is generated by carbon free sources of
electricity. The goal is no longer pure “renewables”, but “carbon free” or
“clean”, which can include wind and solar but also allows for nuclear, hydro,
long-duration storage and bio-gas.

It’s important that a broad portfolio of energy sources is considered,
[particularly nuclear](https://www.platformonomics.com/2022/08/cloud-power-up/),
because the barriers are too high to achieve decarbonization goals with
renewables alone.

![Table comparing different options for clean energy and climate mitigation](options-for-clean-energy.png "Breakdown of options for voluntary clean energy and climate mitigation. From: [Princeton University Zero Lab, 2021](https://www.dropbox.com/s/ela5hwzpb1tzmer/2021-11-16_24-7_Carbon-Free-Electricity.pdf?dl=0)")

## Complex energy systems

Google has been leading the drive towards the 24/7 carbon free energy goal.
Amongst the three big cloud providers, Google has been a consistent leader in
both pushing for 100% renewables and now 24/7 carbon free.

Microsoft has also been doing good work, but perhaps surprisingly, Google has
been the most transparent. [Google is
aiming](https://www.gstatic.com/gumdrop/sustainability/247-carbon-free-energy.pdf)
to match its global data center energy demand by carbon free energy 24/7 by 2030
and has [published a policy roadmap towards
that](https://www.gstatic.com/gumdrop/sustainability/policy-roadmap-carbon-free-energy.pdf).

Unfortunately, it’s not just a case of building out more sources of clean energy
and connecting them to the grid. Keeping the energy system in balance is tricky:
grid operators must ensure that supply continually matches demand. The system
has to deal with changes in weather, demand patterns from normal daily life,
maintenance of equipment, and the fact that electricity is often generated
nowhere near where it needs to be used.

For example, wind generates a lot of electricity in Scotland, [but often needs
to be
curtailed](https://reports.electricinsights.co.uk/q4-2020/record-wind-output-and-curtailment/)
because there is insufficient transmission capacity to move it down to where
demand is in the South.

![Graph showing hourly carbon free energy at an example data center](carbon-free-energy-graph.png "Graph showing the problem with variable renewables on an hourly basis at an example data center. From: [Google, 2020](https://www.gstatic.com/gumdrop/sustainability/247-carbon-free-energy.pdf).")

## System level impacts of 24/7 carbon free energy

Google has funded two studies to look at the impact of 24/7 carbon free energy
on how the grid operates. [The first of these was published in 2021 for the
United States](https://acee.princeton.edu/24-7/) and the second was [recently
published for Europe](https://zenodo.org/record/7180098).

Both of these studies use open source modeling software
([GenX](https://github.com/GenXProject/GenX) for the US and
[PyPSA](https://github.com/PyPSA/PyPSA) for Europe) to create scenarios with
representative demand and a mix of generation technologies. The goal is to see
how the system responds to demand and supply, and in particular to compare cost
and carbon emissions vs the existing model of using 100% annual matching.

The details of the results are worth reading, but my main two takeaways[^carbon] are:

1. Reaching 90-95% carbon free energy can be achieved with only a small cost
   premium compared to 100% annual matching. However, pushing closer to 100%
   significantly increases the cost to more than double.

2. There is a big assumption about the available technologies, including
   long-duration battery/energy storage which has yet to be proven economically
   viable. The price of gas is assumed to be 35 EUR / MWh, which may turn out
   to be wildly optimistic considering [gas futures were >100 EUR / MWh over
   the summer
   2022](https://www.ft.com/content/e11ca7cf-dd7a-43a9-a4e7-0dbd12f244d7).

[^carbon]:
    I’ve ignored the obvious conclusion that moving to 24/7 carbon free
    energy reduces carbon emissions compared to 100% renewables matching on an
    annual basis.

I find it concerning that the success of this approach relies on hand-waving
assumptions about the viability of unproven storage technologies when nuclear is
mentioned only in a footnote for one of the scenarios. It should be a major part
of every scenario. Not including it is consistent with the insane policies of
some European countries to decommission their nuclear plants -
[Germany](https://doomberg.substack.com/p/europe-on-tilt) - but seems like a
missed opportunity to test [the potential of nuclear
energy](https://doomberg.substack.com/p/angels-on-a-pin) for achieving the 24/7
goal.

This is unique to the European study whereas the US modeling includes nuclear as
part of the power generation modeling. It’s a disappointing example of the
negative impact of political decisions following decades of pressure from
self-defeating environmental activists.

## Conclusions

It is notoriously difficult to make projections more than a few years out, but
is necessary given the long lead times for deploying energy infrastructure. It’s
good to see Google funding work to consider grid-wide changes rather than
privately procuring clean energy for itself or relying entirely on questionable
financial instruments to back its marketing. However, the shadow of misguided
anti-nuclear activism is still limiting the technologies under consideration in
Europe.

That said, it is encouraging that both studies (run independently, using
different software) show how it is possible to reach the goals of 24/7 carbon
free energy. As with clean energy generally, the greater the demand the more
opportunity for the market to develop, allowing technologies to be proven, and
prices to eventually fall. That this is being spearheaded by a private company
is worthy of note, but it also highlights that the goals are not just limited by
the limits of technology. Long term storage still needs to be proven, but
nuclear needs to be seriously considered if Europe wants to develop a secure and
sustainable energy grid.
