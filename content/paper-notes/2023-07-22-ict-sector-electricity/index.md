---
title: "Paper Notes - ICT sector electricity consumption and greenhouse gas emissions 2020"
date: 2023-07-22
modified: 2023-07-22
draft: false
tags: ["Paper Notes", "Cloud", "IT Energy", "Data Center Energy", "Network Energy"]
summary: "An updated look at the total electricity consumption and associated 
GHG emissions for the ICT sector in 2020. Paper notes on Malmodin et al. (2023)."
canonicalUrl: https://www.devsustainability.com/p/paper-notes-ict-sector-electricity
url: ict-sector-electricity
---

## Paper

Malmodin, Jens, Nina Lövehagen, Pernilla Bergmark, and Dag Lundén. “ICT Sector
Electricity Consumption and Greenhouse Gas Emissions – 2020 Outcome.” SSRN
Electronic Journal, 2023. <https://doi.org/10.2139/ssrn.4424264>.

## Notes

- This paper presents the most up to date analysis of the electricity
  consumption and associated greenhouse gas emissions of the ICT sector.
- It examines user devices, networks, and data centers, but components such as
  TVs and gaming devices are separated because they tend to fall outside of a
  tight definition of ICT.
- ICT is estimated to account for ~4% of global electricity consumption in 2020.
  - Data center energy consumption is estimated at 223 TWh.
  - Network energy consumption is estimated at 272 TWh.

![A table showing ICT sector use stage electricity consumption](ict-sector.jpg "ICT sector use stage electricity consumption and GHG emissions in 2020,
Malmodin et al., (2023).")

- The full lifecycle of all equipment, including the use stage, translates to
  around 1.4% of global GHG emissions in 2020. The majority of this (57%) is
  from user devices with 37% of the GHG footprint from the embodied emissions.
- Since 2015, total ICT emissions have increased by around 5%. Intensity has
  decreased (efficiency has increased) so per subscriber/user emissions are
  falling, but usage has increased dramatically. This is a classic example of
  the Jevons paradox.

![Graphs showing carbon footprint](ict-sector-graphs.jpg "Development of ICT
sector’s carbon footprint (left), where the dotted lines show the development
without impact from IoT devices, and the total ICT sector footprint per
subscriber (right), Malmodin, et al. (2023).")

![A table showing ICT sector footprint development since 2007 and the present
study](ict-sector-historical.jpg "ICT sector footprint development since 2007
and the present study, Malmodin et al., (2023).")

## Conclusions

The interesting thing about the methodology behind this paper is how much data
has been collected from company reporting. This covers energy consumption as
well as lifecycle assessments from specific products. There is still a
significant modeling component from shipment data, but more and more
organizations are publishing data so the estimates are more accurate.

It’s clear that the ICT industry has been focused on both efficiency (hardware
energy efficiency and software infrastructure) and buying clean energy. This has
resulted in a reduction in use-stage energy per subscription and carbon
footprint per subscription even as usage has dramatically increased from 2007 to 2020. It provides another example of [how wrong extrapolation-based projections
are](https://www.devsustainability.com/p/predictions-in-energy-and-computing).

However, the total footprint is still increasing. More devices are being sold
and most consumers are powering them using non-clean sources of energy. It’s
difficult/impossible for consumers to make much difference here because they
must rely on their local electricity grid to transition to clean energy.

I consider that individual impact on the environment rounds to zero because
although some people will change their behavior, [most
won’t](https://doi.org/10.1177/1469540517717782). If a relatively small number
of manufacturers focus on their supply chain emissions and we continue with the
clean energy transition for data centers and networks, a large portion of the
ICT GHG emissions footprint could be addressed.
