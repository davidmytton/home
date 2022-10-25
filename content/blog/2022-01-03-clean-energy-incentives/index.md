---
title: "Clean energy buying incentives for data centers"
date: 2022-01-03
modified: 2022-01-03
draft: false
tags: ["Data Center Energy"]
summary: "Using a marginal emissions-based sustainability score incentivizes 
migrating workloads to a region with a lower marginal emissions factor. The 
emissions factor for that workload would reduce, but does it incentivize the 
deployment of new clean energy?"
url: clean-energy-buying-incentives-for-data-centers
---

Incentives are the key to understanding all behavior. If you understand the
incentives, you can understand why something has happened or predict what is
likely to happen. That doesn’t mean it’s easy to design good incentives. It’s
notoriously hard. Bad incentives alter behavior in ways that betray their
original goals because the incentive wasn’t properly understood.

Prices act as an incentive. If we want to encourage the adoption of a product,
we can reduce its price or make alternatives more expensive. That works in many
cases, but only if price is the sole incentive.

Other metrics can act as incentives. If we assign a software sustainability
score based on the consumption of clean energy, we can encourage moving
workloads to regions with greater abundance of clean energy. If that score is
calculated on a granular enough basis – by the minute or hour – we can also
encourage workload scheduling at times of more abundant clean energy.

However, the scoring inputs matter.

![Table of renewable energy buyers](clean-energy-2020.png "REBA Deal Tracker:
Top 10 U.S. Large Energy Buyers in 2020
([source](https://www.businesswire.com/news/home/20210210005144/en/REBA-Announces-Top-10-U.S.-Large-Energy-Buyers-in-2020)).")

A sustainability score based on emissions accounting works on an attributional
basis. This considers the impact of individual actions. A data center buying
green power can reduce its own emissions through matching (of whatever type),
thereby improving the sustainability score. Considering only the sustainability
score (ignoring reliability, latency, uptime), there would be an incentive to
move workloads to this data center.

A sustainability score based on marginal emissions works on a consequential
basis. This considers the impact on the system as a whole. A data center buying
green power would have no direct impact on its own emissions and no impact on
the sustainability score for workloads running there. The impact of that green
power depends on whether it is generating as the marginal power plant at any
given time. There would be an incentive to move to that region, but not that
data center.

Therefore, using a marginal emissions-based sustainability score incentivizes
migrating workloads to a region with a lower marginal emissions factor. The
emissions factor for that workload would reduce, but does it incentivize the
deployment of new clean energy?

What is the incentive that encourges data center operators to buy clean energy?
Is it their desire to do good by helping to decarbonize the grid? Maybe. Is it
because their customers and regulators are applying pressure? More likely, and
this is growing. I’d bet on the latter, not the former. Competitive advantage
leads to customer demand.

Assessing grid emissions on a consequential basis is a good approach for
systems-level thinking and overall decarbonization goals. But who is buying all
the clean energy? What is the goal of a sustainability score? Is it to reduce
the emissions impact of a specific workload? Or is it trying to encourage system
level decarbonization? If the latter, can a sustainability score based on
marginal emissions that ignores the actions of individual data centers achieve
that?
