---
title: "Overestimating AI's water footprint"
date: 2023-04-17
modified: 2023-04-19
draft: false
tags: ["Data Center Water", "Cloud", "AI", "Transparency"]
summary: "Researchers need to be more careful about the inputs into their models. Overestimates undermine the goal of reducing the environmental impact of IT."
canonicalUrl: https://www.devsustainability.com/p/overestimating-ais-water-footprint
url: overestimating-ai-water-footprint
---

Last week, a journalist requested that I comment on [a new preprint
article](https://arxiv.org/pdf/2304.03271v1.pdf) discussing the water footprint
of AI. Water is a crucial subject, as the discussion about the environmental
impact of IT has mainly centered around energy and carbon emissions, a
limitation I addressed [in a 2021
article](https://doi.org/10.1038/s41545-021-00101-w).

I agree with the preprint's conclusions that data center water consumption is
often an overlooked aspect, with data center operators traditionally treating it
as a trade secret. We need to better understand the full environmental footprint
so we can model whether strategies like [demand
response](https://www.devsustainability.com/p/why-dont-data-centers-demand-response)
or load shifting are worth it ([maybe
not](https://adrianco.medium.com/dont-follow-the-sun-scheduling-compute-workloads-to-chase-green-energy-can-be-counter-productive-b0cde6681763)).
Although major companies like
[Microsoft](https://blogs.microsoft.com/on-the-issues/2023/03/22/water-positive-climate-resilience-open-call/)
and
[Google](https://blog.google/outreach-initiatives/sustainability/our-commitment-to-climate-conscious-data-center-cooling/)
are becoming more transparent about their water usage, comprehensive data on the
water footprint of large data centers is still lacking

However, the study's reported figures likely overestimate actual consumption.
They describe an average on-site Water Usage Effectiveness (WUE) of 3.8-5.2
L/kWh based on [a WSJ article from
2015](https://www.wsj.com/articles/data-centers-1435168386) referencing [a
presentation from
2009](https://mvdirona.com/jrh/TalksAndPapers/JamesHamilton_Google2009.pdf) (the
lower number) and [an online post in
Chinese](https://blog.csdn.net/j6UL6lQ4vA97XlM/article/details/126112615) (the
higher number). Their model utilizes generic commercial cooling tower
specifications and weather data. While the actual figures are not provided (a
footnote, strangely not in the methodology section, explains a range of
“0.5L/kWh and 5L/kWh depending on weather conditions”), the paper's August 2022
on-site WUE graphs indicate ranges of ~3.8-6.2 L/kWh, depending on location.

![Image of graphs](wue-by-location.png "Hourly carbon efficiency and on-site WUE
for the first week of August 2022, from Figure 5 in “Making AI Less “Thirsty”:
Uncovering and Addressing the Secret Water Footprint of AI Models”
([source](https://arxiv.org/pdf/2304.03271v1.pdf)).")

This is an interesting approach because data center operators do not publish
granular data, so they have tried to infer it. However, the use of generic
equipment likely misses the efficiencies that exist in hyperscale data centers.

[Research from
2016](https://eta.lbl.gov/publications/united-states-data-center-energy)
suggests the average US data center WUE is 1.8 L/kWh, while Facebook (Meta), an
industry leader in data center water footprint, reports 0.26 L/kWh
([pg39](https://sustainability.fb.com/wp-content/uploads/2022/06/Meta-2021-Sustainability-Report.pdf)).
[Microsoft’s WUE
ranges](https://azure.microsoft.com/en-us/blog/how-microsoft-measures-datacenter-water-and-energy-use-to-improve-azure-cloud-sustainability/)
from 0.1 L/kWh (EMEA) to 1.65 L/kWh (Asia Pacific), with the Americas sitting in
the middle (0.55 L/kWh). Google's efficiency is likely similar, making the
graphed values excessive.

![Graph of Facebook WUE](fb-wue.png "Annual data center water usage
effectiveness, from[ Meta’s Sustainability report
2021](https://sustainability.fb.com/wp-content/uploads/2022/06/Meta-2021-Sustainability-Report.pdf).
The axis appears mislabeled and should be L/kWh of IT power.")

It is also crucial to contextualize data center water usage in relation to other
industries. Billions of liters may seem like a lot, but understanding
location-specific water stress is vital. While the paper mentions this, it does
not thoroughly explore the topic alongside its results. In comparison to other
industries, data centers consume relatively little water. All water counts, but
how much it counts has to be considered relative to the local resources. Unlike
carbon, [zero water is not necessarily the goal](https://davidmytton.blog/zero-water-in-our-data-centers-by-2030-mission-impossible/).

Being a preprint, the article may undergo significant changes before
publication, if it is published at all1. However, this is another example of
selecting the high end of a range of possible input values to suit a particular
narrative. We’ve seen similar scare tactics used when discussing [“digital
sobriety”](https://www.devsustainability.com/p/value-judgments-and-sustainable-computing)
in relation to extreme projections for future IT energy usage.

Perhaps a revised version could compare the estimates from the commercial
cooling specs alongside the industry average and reported values from Facebook.
That would be an interesting illustration. The methodology also needs
clarification - different numbers are cited at different points, the ranges are
wide, and the graphs in the appendix aren't helpful in understanding the actual
values used in the calculations.

Researchers must exercise caution when selecting model inputs, avoiding the
temptation to adopt the highest possible value. They should show the range.
Overestimates only undermine the credibility of vital environmental research
topics.
