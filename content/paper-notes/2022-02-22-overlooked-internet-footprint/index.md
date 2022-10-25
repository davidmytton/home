---
title: "Paper Notes – The overlooked environmental footprint of increasing Internet use"
date: 2022-02-22
draft: false
tags: ["Paper Notes", "Cloud", "IT Energy", "Data Center Energy", "Network Energy"]
summary: "The methodology is invalid, which the authors acknowledge but ignore. 
This means the results of this article aren’t particularly useful."
url: paper-notes-the-overlooked-environmental-footprint-of-increasing-internet-use
---

## Paper

Obringer, R., Rachunok, B., Maia-Silva, D., Arbabzadeh, M., Nateghi, R., and
Madani, K. (2021). The overlooked environmental footprint of increasing Internet
use. Resour. Conserv. Recycl. *167*,
105389. <https://doi.org/10.1016/j.resconrec.2020.105389>

## Notes

- The article itself has no abstract and is very short. I assume this is because
  it is a “Perspective” article, so most of what is worth looking at is
  contained within the supplementary materials.
- The article makes an estimate of the carbon, water and land footprints of
  fixed-line internet use. It estimates that “Globally, the Internet use has a
  carbon footprint ranging from 28 to 63 g CO2 equivalent per gigabyte (GB),
  while its water and land foot-prints range from 0.1 to 35 L/GB and 0.7 to 20
  cm2/GB, respectively”.
- The system boundary only includes fixed-line networks, thereby excluding all
  end-user devices as well as mobile connections. This is a valid system
  boundary, but excluding mobile devices misses a major source of network
  traffic.
- The value for energy intensity of the network traffic is taken from [Aslan,
  2018](http://doi.wiley.com/10.1111/jiec.12630). This matches the system
  boundary (Aslan only considers fixed-line networking). However, they do not
  make any adjustments to the energy efficiency. Aslan clearly states that the
  trend is for network energy to fall by 50% every 2 years, but that is not
  taken into account.
- A reference is also made to “[The carbon footprint of streaming video:
  fact-checking the
  headlines](https://www.iea.org/commentaries/the-carbon-footprint-of-streaming-video-fact-checking-the-headlines)”
  from the IEA, but the network energy intensity values do not appear to be
  taken from that article. The IEA give a figure of 0.002 kWh/GB, but Obringer
  et al use 0.06 kWh/GB (which is the value for 2015 from Aslan).
- They include data centers as a component of the calculation, but use network
  traffic as a proxy for the energy consumption at an intensity of 0.01 kWh/GB.
  I couldn’t figure out where this number comes from. This results in a per GB
  energy intensity figure, including the data center, rather than a total figure
  of annual data center (or network) energy consumption.
- Calculations are made based on an assumed linear correlation between network
  traffic and energy consumption. Energy intensity factors are multiplied by
  hourly estimated data transmission volumes for a range of applications. This
  includes the data center component, which doesn’t make much sense – data
  volume is rarely related to the energy consumption of a data center – servers,
  storage, etc because there are too many other processes involved. Transmission
  of 1GB of data could result in optimization, rendering, machine learning
  training and inference, redundant storage and replication, extraction of just
  a single value from that data…and so on.
- However, they also state:

> In practice, energy use for data storage and transmission does not increase
> linearly with increased internet use. Our estimation disregards this
> nonlinearity and relies on average energy use per gigabyte of data… Similarly,
> the footprints of energy production do not change linearly with increased
> energy use. Our estimations disregard this nonlinearity as well as other
> factors, such as the change in the energy mix by the change in level of
> production or hour of use (e.g., during peak hours).

- Even though they reference three other publications which they claim to take
  the same approach, this assumption invalidates their whole methodology. It
  seems very strange that you would acknowledge that there is no linear
  correlation between network energy and data transmission, then disregard that
  and proceed with an approach on the basis that there is a correlation. [The
  IEA
  source](https://www.iea.org/commentaries/the-carbon-footprint-of-streaming-video-fact-checking-the-headlines) they
  cite to back up this approach specifically says “the [latest
  research](https://online.electronicsgoesgreen.org/session/) shows that
  these *data-based* intensity values (kWh/GB) are [not
  appropriate](https://youtu.be/Xo0PB5i_b4Y?t=2504) for estimating the network
  energy use of high bitrate applications such as streaming video”.
- At the time of writing, the IEA article was referring to informal sources to
  make that statement. These have now been published more formally, such as
  in [Malmodin,
  2020](https://online.electronicsgoesgreen.org/wp-content/uploads/2020/10/Proceedings_EGG2020_v2.pdf) and [Koomey
  & Masanet, 2021](https://dx.doi.org/10.1016/j.joule.2021.05.007).
- There is an argument to be made that there will be an increase in energy
  consumption as network traffic increases, just it is not likely to be linear.
  Network operators provision for peak load, and redundancy, so growth in
  traffic will eventually result in new network equipment being deployed to cope
  with that increase. This may result in a decrease in energy intensity (newer
  equipment can handle more traffic), but it may need more equipment to be
  deployed (so an increase in the absolute energy consumption).
- Obringer et al. do not make that argument.

## Conclusions

Unfortunately the methodological flaws mean the results aren’t useful.
