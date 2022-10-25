---
title: "How much energy will 5G consume?"
date: 2020-09-18
modified: 2020-10-07
draft: false
tags: ["Network Energy", "IT Energy", "Energy Efficiency"]
summary: "5G networks have larger antennas, larger bandwidths, and higher base 
station density. This means up to x3 more energy consumption. How can the 
industry expect x20 more energy efficiency by 2030?"
url: how-much-energy-will-5g-consume
---

5G is the next generation of mobile communication technology which started
rolling out in 2019 and is planned to replace 4G over the coming decade. You may
have heard about the idiotic conspiracy theories about 5G and burning cell
towers ([BBC, 2020](https://www.bbc.co.uk/news/52168096)), but prior to CVOID
the hype focused on the main benefit of speed: download speeds are expected to
be up to 10Gbit/s ([Hoffman,
2019](https://www.howtogeek.com/340002/what-is-5g-and-how-fast-will-it-be/))
compared to less than 1Gbit/s for 4G ([ITU,
2008](http://www.itu.int/pub/R-REP-M.2134-2008/en)). I have measured 4G speeds
of over 100MB/s in central Tokyo, but otherwise I expect that type of
performance is rare! It will be more likely with 5G.

The improved 5G speeds are achieved through higher-frequency radio waves, but
they have shorter ranges. 3 different types of antenna will support 3 different
frequencies to allow operators to trade-off range with speed, with devices
selecting the highest speed option in range. The fastest speeds are available
from the highest frequency (mmWave). These will be deployed in dense urban areas
but the lower range means more cells are required.

Although some networks have started advertising 5G connectivity, this tends to
be the lower-speed frequency, few devices offer 5G support, and those that
do [tend to be awful](https://www.youtube.com/watch?v=_CTUs_2hq6Y). This will
change by 2025 when it is suggested that 2.8 billion 5G subscriptions will
exist, accounting for 30% of all mobile subscriptions. 4G will peak in 2022 at
5.1 billion subscriptions ([Ericsson,
2020](https://www.ericsson.com/en/mobility-report/reports/june-2020/mobile-subscriptions-outlook)).
We will know when 5G is ready when Apple include it in the iPhone.

![Mobile subscriptions by technology](mobile-subscriptions.jpg "Mobile subscriptions by technology (billion) ([Ericsson, 2020](https://www.ericsson.com/en/mobility-report/reports/june-2020/mobile-subscriptions-outlook)).")

All sounds good, until you consider energy consumption. In a study of Finland,
which has some of the highest mobile data consumption in the world, mobile
networks were reported as being responsible for 0.7% of annual electricity
consumption, 0.6 TWh in 2017 ([Pihkola et al,
2018](https://doi.org/10.3390/su10072494)). The study also showed that energy
efficiency improved from 12.34 kWh/GB in 2010 to 0.30 kWh/GB in 2017. Although
efficiency is improving, more data is being transmitted.

![Development of energy efficiency of transmitted mobile data](network-energy-intensity.png "Development of energy efficiency of transmitted mobile data (kWh/gigabyte) in Finland during 2010–2017 ([Pihkola et al, 2018](https://doi.org/10.3390/su10072494)).")

Indeed, this is what has happened with the rollout of all mobile technologies –
from 2G through to 5G – resulting resulting in an overall increase in total
energy consumption ([Joshi,
2019](https://www.ericsson.com/en/blog/2019/2/breaking-the-energy-curve-5g-energy-efficiency); [Han
& Bian, 2020](https://doi.org/10.1038/s41928-020-0404-1)). An industry survey
supports this view, suggesting that 94% of respondents expect 5G to increase
energy costs ([451 Research,
2019](https://www.vertiv.com/globalassets/documents/white-papers/451-research-paper/10648_advisory_bw_vertiv_266274_0.pdf)).
This is a manifestation of [Jevon’s
Paradox](https://en.wikipedia.org/wiki/Jevons_paradox).

![Energy performance](network-energy-performance.png "Energy performance ([Joshi,
2019](https://www.ericsson.com/en/blog/2019/2/breaking-the-energy-curve-5g-energy-efficiency)).")

The industry is aiming for 5G to be x20 more energy efficient than 4G by 2030
([Orange,
2020](https://hellofuture.orange.com/en/5g-energy-efficiency-by-design/)). There
are several features in 5G that are hoped to reduce energy consumption, such as
more efficient software ([Ericsson,
2020](https://www.ericsson.com/495d5c/assets/local/about-ericsson/sustainability-and-corporate-responsibility/documents/2020/breaking-the-energy-curve-report.pdf)),
but the main focus is on new sleep mode functionality. 4G networks must send
signals every 1ms whereas 5G can do so every 20ms. During idle periods (such as
in the early morning), this can significantly reduce unnecessary transmissions
([Frenger & Tano,
2019](https://www.ericsson.com/en/blog/2019/9/energy-consumption-5g-nr); [Dahlman
& Parkvall, 2018](https://ieeexplore.ieee.org/document/8417851); [Lähetkangas et
al, 2014](https://doi.org/10.1109/ICCW.2014.6881163)).

![Example of base station energy consumption during idle mode](base-station-sleep.jpg "Example of base station energy consumption during idle mode signaling in LTE (top) and 5G NR (bottom). NR is configured to send signal blocks (SSB) every 20 ms ([Frenger & Tano, 2019](https://www.ericsson.com/en/blog/2019/9/energy-consumption-5g-nr)).")

The German Federal Environment Ministry and the German Environment Agency
released a joint report on the climate footprint of video streaming ([Umwelt
Bundesamt,
2020](https://www.umweltbundesamt.de/en/press/pressinformation/video-streaming-data-transmission-technology))
which also examined 5G. The report is in German so it is difficult for me to
analyse e.g. whether the carbon footprint included the manufacturing of devices,
but the English press release shows HD video streaming over fibre connectivity
generated 2g CO2/hr, 5g CO2/hr for 5G and 90g CO2/hr for 3G. Wired connectivity
is always going to be the least energy intensive method of connectivity because
it doesn’t involve radio transmission, but 5G performs very well in comparison.

However, the end-user device is excluded from the methodology. Historical
studies have reported that the majority of energy is consumed by the end-user
device and transmission network ([Shehabi, Walker & Masanet,
2014](https://doi.org/10.1088/1748-9326/9/5/054007)). The impact on the device
battery is being discussed as a reason why 5G may consume x3 more energy than 4G
([Koziol,
2019](https://spectrum.ieee.org/telecom/wireless/5gs-waveform-is-a-battery-vampire)).

Past studies show that base stations are responsible for 57% of power
consumption ([Han et al, 2011](https://doi.org/10.1109/MCOM.2011.5783984)). It
is assumed this means the radio transmission because compute requirements were
historically smaller and fixed as a constant ([Samarakoon,
2016](https://doi.org/10.1109/JSAC.2016.2545539)), but compute overhead
increases with larger traffic volumes over more base stations. Moving processing
to the edge will also increase the compute requirements and subsequent energy
allocation. An analysis of the compute and transmission overheads suggest this
will shift the balance so that more than 50% of energy will be consumed by
compute resources in 5G base stations ([Ge et al,
2017](https://doi.org/10.1109/MCOM.2017.1600788)).

![Computation power of base stations](base-station-computation-power.gif "Computation power of base stations (BSs) with respect to the number of antennas and bandwidths ([Ge et al, 2017](https://doi.org/10.1109/MCOM.2017.1600788)).")

Improving the energy consumption of 5G networks is going to be a combination of
options, with tradeoffs around speed and range. [Wu et al,
2017](https://doi.org/10.1109/MWC.2017.1600343) proposes several options ranging
from making beam forming antennas more efficient and centralising signal
processing, through to statistical models that manage packet queuing based on
the availability of renewable energy. Smarter orchestration of workloads could
consider the energy (and bandwidth) cost of backhauling traffic to centralised
data centres vs performing processing closer to (or at) the edge ([Zhang et al,
2016](https://doi.org/10.1109/ACCESS.2016.2597169); [Yang et al,
2018](https://doi.org/10.1109/TVT.2018.2799620)). This is interesting [when
combined with serverless event driven
architectures](https://davidmytton.blog/energy-efficiency-edge-compute-and-serverless/).

The challenge with 5G energy consumption is a function of the design: larger
antennas, larger bandwidths, and higher base station density ([Han & Bian,
2020](https://doi.org/10.1038/s41928-020-0404-1)). However, compared to when 4G
was rolling out, energy consumption and the associated environmental/climate
impacts now attract much more public interest and media attention. This will be
a positive forcing function on the industry.
