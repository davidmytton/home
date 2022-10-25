---
title: "Paper notes – Jupiter Evolving: Transforming Google’s Datacenter Network"
date: 2022-09-21
modified: 2022-09-21
draft: false
tags: ["Paper Notes", "IT Energy", "Network Energy"]
summary: "Removing the aggregation spine resulted in 5x higher speed and 
capacity, and 41% reduction in power."
url: paper-notes-jupiter-evolving-transforming-googles-datacenter-network
---

## Paper

Poutievski et al, 2022. Jupiter Evolving: Transforming Google’s Datacenter
Network via Optical Circuit Switches and Software-Defined Networking, in:
Proceedings of ACM SIGCOMM 2022. Presented at the SIGCOMM’22, Amsterdam,
Netherlands. <https://doi.org/10.1145/3544216.3544265>

## Notes

- This is a technical paper which describes the evolution of Google’s internal
  networking architecture, known as Jupiter. It’s mostly focused on the design
  and operation of the network, but has some interesting lessons relating to
  power consumption.
- The main energy-relevant innovation[^otherchanges] is the move from a [Clos network
  design](https://en.wikipedia.org/wiki/Clos_network) to a direct-connect
  topology among the machine aggregation blocks. This removes the aggregation
  spine, which means the associated switches and optical networking components
  are no longer needed.
  - The other changes included switching to optical circuit switches and a
    centralized SDN control plane.
- The removal of the spine sections is responsible for the majority of reduced
  power consumption, resulting in 5x higher speed and capacity, 30% reduction in
  capex[^capex] and 41% reduction in power.
  - There is also the associated embodied energy in the equipment that no longer
    needs to be deployed. This isn’t a lifecycle analysis paper, so that isn’t
    considered other than in capex.
- In the past, power consumption had fallen even as capacity increased, allowing
  for improved network energy efficiency. However, those gains were slowing.

![Graph of diminishing returns in power consumption](network-power-consumption.png "Diminishing returns in power consumption normalized to bandwidth (pJ/b) for successive generations of switches and optics (normalized to the 40Gbps generation). **Source:** [Poutievski et al (2022).](https://doi.org/10.1145/3544216.3544265)")

- The expected diminishing returns might have [led some to
  predict](https://davidmytton.blog/approaches-to-calculating-network-website-energy-and-carbon/)
  that we’d see an energy efficiency plateau even as demand continues to
  increase. Instead, we have a major shift in approach which means power
  consumption is not following those expectations.
- This is important because many predictions of high power consumption by data
  centers, networks, and IT in general, extrapolate from past trends. A point
  made in [the recent Joule paper I
  co-authored](https://doi.org/10.1016/j.joule.2022.07.011) discussed how
  technology trends are the source of considerable uncertainty.

[^otherchanges]:
    The other changes included switching to optical circuit
    switches and a centralized SDN control plane.

[^capex]:
    There is also the associated embodied energy in the equipment that no
    longer needs to be deployed. This isn’t a lifecycle analysis paper, so that
    isn’t considered other than in capex.

## Conclusions

We can’t rely on these types of technology improvements precisely because they
are so unpredictable, but this is a good example of the right incentives pushing
innovation in the right direction. The challenge is how to model them – making
predictions more than a few years (or even just 6-12 months!) into the future is
[generally a bad
idea](https://davidmytton.blog/predictions-in-energy-and-computing/).
