---
title: "Paper notes – Moore’s Law and ICT Innovation in the Anthropocene"
date: 2021-03-08
modified: 2021-03-08
draft: false
tags: ["Paper Notes", "IT Energy", "Hardware", "Energy Efficiency"]
summary: "My notes on the paper: Bol, D., Pirson, T. & Dekimpe, R. (2021) 
Moore’s Law and ICT Innovation in the Anthropocene."
url: paper-notes-moores-law-and-ict-innovation-in-the-anthropocene
---

I get Google Scholar alerts for new publications searching against a few
different keywords related to sustainable computing. This usually emails me 2-5
new papers each week, of which maybe 1-2 are relevant / sound interesting. I aim
to read one per week, take notes, make highlights, and try to stay up to date
with the latest research.

I thought it may be useful to publish my notes as I go, so this will be an
ongoing series.

## Paper

Bol, D., Pirson, T. & Dekimpe, R. (2021) *Moore’s Law and ICT Innovation in the
Anthropocene*. Available
from: <https://dial.uclouvain.be/pr/boreal/object/boreal%3A243578/datastream/PDF_01/view>

## Abstract

> In information and communication technologies (ICTs), innovation is
> intrinsically linked to empirical laws of exponential efficiency improvement
> such as Moore’s law. By following these laws, the industry achieved an amazing
> relative decoupling between the improvement of key performance indicators
> (KPIs), such as the number of transistors, from physical resource usage such
> as silicon wafers. Concurrently, digital ICTs came from almost zero greenhouse
> gas emission (GHG) in the middle of the twentieth century to direct annual
> carbon footprint of approximately 1400 MT CO2e today. Given the fact that we
> have to strongly reduce global GHG emissions to limit global warming below
> 2°C, it is not clear if the simple follow-up of these trends can decrease the
> direct GHG emissions of the ICT sector on a trajectory compatible with Paris
> agreement.
>
> In this paper, we analyze the recent evolution of energy and carbon footprints
> from three ICT activity sub-sectors: semiconductor manufacturing, wireless
> Internet access and datacenter usage. By adopting a Kaya-like decomposition in
> technology affluence and efficiency factors, we find out that the KPI increase
> failed to reach an absolute decoupling with respect to total energy
> consumption because the technology affluence increases more than the
> efficiency. The same conclusion holds for GHG emissions except for
> datacenters, where recent investment in renewable energy sources lead to an
> absolute GHG reduction over the last years, despite a moderate energy
> increase.
>
> We formulate hypotheses for this absence of absolute decoupling from three
> scientific fields: ecological economics, economics of technology and sociology
> of technology. We argue that aligning direct GHG emissions of the ICT sector
> on a trajectory compatible with Paris agreement requires an ecological
> transition in innovation by adopting sobriety in addition to efficiency.

## Notes

- This paper draws on 6 studies which examine global ICT footprint. They
  summarise the findings as: annual electricity consumption and GHG emissions
  of approximately 1400TWh and 1400MTCO2e for the ICT sector today. However,
  only 2 of those studies have received peer review (which the authors note in
  the table) and there is no discussion of the definition of “ICT”, which may
  vary across the studies.
- Energy consumption is easier to estimate because it can be measured. Annual
  GHG emissions from ICT tend to be linked to energy consumption but they are
  only a snapshot because the emissions factors related to energy consumption
  change over time. The authors note this later in the paper in relation to
  data centers and the investments in renewable energy that powers them.
- The authors note that for GHG emissions to fall, we need to consider the
  full lifecycle. This varies depending on the item you are measuring, such
  as [servers, which have large use-stage emissions vs user devices which tend
  to have large manufacturing
  emissions](https://davidmytton.blog/carbon-footprint-laptops-vs-servers-intel-vs-arm/).
- The key question of the paper is whether efficiency improvements will be
  helpful to reduce emissions, and in particular whether the expected ICT
  usage increases are decoupled from the carbon emissions associated with that
  usage. Can we reduce carbon emissions as we use more and more ICT services?
- **Semiconductors:** Transistor density is increasing as dimensions reduce,
  from 90nm down to the current cutting edge 5nm sizes. These smaller
  transistors are much more complex to manufacture and the energy required in
  the processes has increased by 12-20% annually. Semiconductor manufacturing
  is probably the most complex industrial ever created, so it is not
  surprising that chip production makes up a large share of the energy and
  carbon footprint of electronics manufacturing.
- The paper also considers the physical limits the ICT industry is rapidly
  approaching, for example semiconductor transistor sizes cannot go below the
  size of a single atom. What happens when we reach that limit and cannot make
  chips more efficient?
- **Mobile internet access:** Is growing rapidly, particularly because
  developing countries are skipping many of the stages of telecoms deployment
  that more developed countries have gone through. More people are coming
  online and they are using 4G mobile technology to do so. 5G will grow
  rapidly over the coming years, but [despite the potential for energy
  efficiency
  improvements](https://davidmytton.blog/how-much-energy-will-5g-consume/),
  the ability to transmit more data, faster i.e. more efficiently, that
  doesn’t mean total energy consumption will decrease.
- **Data centers:** Efficiency improvements over the last 10 years have been
  enough to offset increased energy consumption so that the total growth
  estimates range
  between [0.7%](https://science.sciencemag.org/content/367/6481/984) and [6.5%](https://www.borderstep.de/publikation/hintemann-r-hinterholzer-s-2019-energy-consumption-of-data-centers-worldwide-how-will-the-internet-become-green-presented-at-ict4s-lappeenranta-finland/) per
  year. However, this appears to be slowing.

## Conclusions

The paper concludes that there is no evidence to support a decoupling of carbon
emissions from economic growth on a global scale, but highlights data centers as
an interesting example because that sector has shown it is possible (depending
on which estimate you look at). This improvement is mainly driven by the
hyperscale providers who are purchasing large amounts of renewable energy, but
the paper notes that this may not scale to other industries:

> ..if we consider a non ideal market which is likely to be the reality, the
> low-carbon energy purchased by datacenter operators may no longer be available
> for other sectors. In this case, the decoupling remains local and limited GHG
> reduction is achieved at the global scale because the energy footprint is not
> decreasing.

Further, as we make more efficient equipment, there is a tendency to throw away
old items to get the new shiny thing. This may make sense if the majority of the
emissions come from the use-stage, but that is not the case for consumer devices
where this forced obsolescence tends to manifest.

The paper makes an important conclusion that focus on ever more efficient
technologies is not going to help us reduce our carbon footprint. This is the
classic example of the [Jevons
Paradox](https://en.wikipedia.org/wiki/Jevons_paradox).

Finally, the paper discusses the concept of “speculative faith in technology”:

> We thus define KPI-driven innovation as the blind habit for ICT engineers and
> companies to pursue the increase of any KPI such as number of CPU cores,
> number of artificial neurons, number of pixels in a CMOS imager, number of
> imagers in a smartphone, with the unconscious faith that it will lead to
> future valorization. Secondly, disruption of the present by technological
> innovation is a key speculative practice to invent a future that is supposed
> to ”change everything” and absorb the debts of the present.

Whilst it is true that this kind of innovation for the sake of innovation
buzzwords is not ideal, this argument is not developed further. It sounds like a
criticism of the cliche Silicon Valley startup parodied in the mainstream press
rather than a specific criticism backed by examples. There will always be people
chasing the latest shiny things – it’s impossibe to know in advance what will
and won’t work. Their argument that this is a negative shows a misunderstanding
of the startup process, and how technological innovation works. I’m not sure why
this was included in an otherwise interesting paper.
