---
title: "Paper notes – A systematic review of the costs and impacts of integrating variable renewables into power grids"
date: 2021-05-21
modified: 2021-05-21
draft: false
tags: ["Paper Notes", "Renewables Transition"]
summary: "My notes on the paper: Heptonstall, P.J. & Gross, R.J.K. (2021) A 
systematic review of the costs and impacts of integrating variable renewables 
into power grids. Nature Energy. 6 (1), 72–83."
url: paper-notes-a-systematic-review-of-the-costs-and-impacts-of-integrating-variable-renewables-into-power-grids
---

### Paper

Heptonstall, P.J. & Gross, R.J.K. (2021) A systematic review of the costs and
impacts of integrating variable renewables into power grids. *Nature Energy*. 6
(1), 72–83. Available from:
doi: [10.1038/s41560-020-00695-4](https://doi.org/10.1038/s41560-020-00695-4).

### Abstract

> The impact of variable renewable energy (VRE) sources on an electricity system
> depends on technological characteristics, demand, regulatory practices and
> renewable resources. The costs of integrating wind or solar power into
> electricity networks have been debated for decades yet remain controversial
> and often misunderstood. Here we undertake a systematic review of the
> international evidence on the cost and impact of integrating wind and solar to
> provide policymakers with evidence to inform strategic choices about which
> technologies to support. We find a wide range of costs across the literature
> that depend largely on the price and availability of flexible system
> operation. Costs are small at low penetrations of VRE and can even be
> negative. Data are scarce at high penetrations, but show that the range
> widens. Nonetheless, VRE sources can be a key part of a least-cost route to
> decarbonization.

### Notes

- This paper is not directly about sustainable computing but covers a relevant
  topic – what happens to the electricity grid as more renewables are added?
  Wind and solar energy is variable – the output can change relatively quickly
  – and is not dispatchable – you can’t choose when it generates. This poses
  operational challenges as we add more and more to the grid.
- This is relevant to computing, and data centres in particular, because compute
  workloads generally need highly reliable sources of electricity. Data
  centres are designed with multiple systems of redundancy which include
  batteries and backup generators. If the grid becomes more unstable as
  renewables increase, this poses a problem for data centre operators.
- Renewables penetration is expected to increase over the coming years. For
  example, in Ireland and Denmark, they expect wind and solar to form the
  majority of generation capacity by 2030.
  - Currently in Ireland and Northern Ireland, the maximum energy from wind and
    solar is 65%, but this is going to increase to 75% by the end of 2021
    and 95% by 2030. Ireland’s physical location at the edge of Europe and
    the weather caused by the jet stream result in forecast challenges where
    errors can affect a significant part of demand. Ramping margins are
    being used to bridge this gap
    ([source](http://www.eirgridgroup.com/site-files/library/EirGrid/All-Island-Generation-Capacity-Statement-2020-2029.pdf)).
  - In Denmark they expect to be at 54% renewables by 2030, but electricity
    generation will be 109% renewables by 2030 (which means domestic
    production exceeds domestic consumption, so Denmark will be a large net
    exporter of electricity from 2026 onwards)
    ([source](https://ens.dk/sites/ens.dk/files/Analyser/deco19.pdf)).
- This is a challenge because a large part of the demand growth on the grid in
  Ireland and Denmark is expected to come from data centres.
  - Ireland: Median demand scenario projects data centres making up to 27% of
    total grid demand by 2029, outpacing industrial users. Typical load is
    40% of contracted Maximum Input Capacity, which is expected to grow as
    data centres build
    out ([source](http://www.eirgridgroup.com/site-files/library/EirGrid/All-Island-Generation-Capacity-Statement-2020-2029.pdf)).
  - Denmark: Data centres grow from 1% to 15% of total energy demand, 7 TWh, by 2030. Growth in industry and services is 80% from data centres
    ([source](https://ens.dk/sites/ens.dk/files/Analyser/deco19.pdf)).
- [Some](https://www.iea.org/commentaries/5-ways-big-tech-could-have-big-impacts-on-clean-energy-transitions) see
  this as an opportunity for data centres to participate in demand response
  but [others](https://journal.uptimeinstitute.com/renewable-energy-and-data-centers-buyer-be-aware/) see
  these grid challenges as a reason to be cautious about renewables for data
  centres – issues of grid reliability are not well understood by energy
  buyers, and claims have been made that falling spot prices hurt the business
  models of energy businesses and their ability to invest in reliability.
- The review by Heptonstall & Gross looks at a significant body of literature to
  examine the cost of increasing the penetration of renewables on the grid.
  These costs cover various categories such as systems integration,
  transmission and distribution, curtailment and reserve costs. The results
  show that up to around 50% penetration the costs are relatively small.
  However, past 50% there is limited evidence, probably because few
  electricity grids have reached such a high level of renewables penetration.

![Graph of costs](heptonstall-gross-fig2.png "Data for operating reserve,
capacity adequacy, aggregated and profile costs from [Heptonstall & Gross
(2021)](https://doi.org/10.1038/s41560-020-00695-4).")

- Data centre demand response has been a topic of academic interest for over a
  decade. Data centres could participate in “ancillary service markets” as a
  load resource to help with the balance of supply and demand e.g.
  increasing/decreasing demand (and being paid to do so) ([Wierman *et al.*,
  2014](https://doi.org/10.1109/IGCC.2014.7039172)). Past models have focused
  on profit ([Ghamkhari & Mohsenian-Rad,
  2012](https://doi.org/10.1109/SmartGridComm.2012.6486023); [Liu *et al.*,
  2014](https://doi.org/10.1145/2637364.2592004)) but is that the motivation
  for data centres?
- Field tests were carried out in 2012 – not particularly large participants
  (550 kW – 2.3 MW) – but they showed up to 25% demand savings available. Also
  showed similar data centres can participate with no damage to SLAs
  ([Ghatikar *et al.*, 2012](https://escholarship.org/uc/item/7bh6n6kt)).
  However, there are challenges with market design because markets assume
  customers are price takers whereas data centre loads are so high they are
  often price makers ([Liu *et al.*,
  2014](https://doi.org/10.1145/2637364.2592004)).
- Given that the demand response flexibility for a small (30MW) data centre was
  modelled to be worth between $500,000 – $5,000,000 almost a decade
  ago ([Wierman *et al.*, 2014](https://doi.org/10.1109/IGCC.2014.7039172)),
  and data centres have become larger and more automated/sophisticated, why
  has demand response from data centres not become more popular? My thoughts
  are that:
  - Reliability is a higher priority than energy efficiency.
  - Timing of demand response from the grid do not correlate well with periods
    of high load for the DC.
  - Participating in the market for these systems is very complex and difficult
    to incorporate into the data centre management systems.
- Participating in demand response is difficult for colo providers ([Ren &
  Islam, 2014](https://doi.org/10.1145/2695533.2695559)) – colo pricing is
  based on peak power rather than actual usage – but what is the impact of
  hyperscale cloud where design guidelines assume failure?
- “The cloud” is an abstraction of physical resources. Architecture best
  practices for cloud applications always emphasise the importance of assuming
  failure. If cloud zones and regions are used correctly, they could allow the
  movement of demand based on signals, such as from spot instance prices.
  Hyperscale providers operate at such a scale that the cost savings from the
  grid could become worth it.
- Either way, more research is needed to fully understand the impact of high
  renewables penetration on energy systems. For data centres in particular,
  this means examining grid reliability and market design to encourage
  participation in demand response.
