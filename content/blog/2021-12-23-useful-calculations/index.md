---
title: "Useful calculations – energy vs carbon"
date: 2021-12-23
modified: 2021-12-23
draft: false
tags: ["IT Energy", "Energy Efficiency"]
summary: "The ultimate goal is a reduction in emissions, but we can’t analyze 
improvements without reporting energy per unit of work done."
url: useful-calculations-energy-vs-carbon
---

We care about emissions because carbon dioxide and its other greenhouse gas
(GHG) equivalents are responsible for climate change. You might therefore think
that reporting emissions is all that is necessary. Simply tell everyone how much
CO2e you were responsible for and when it hits (and stays at) zero, everything
is great.

This is true to the extent that there is a global target. We want to hit global
net zero to stabilize atmospheric carbon levels, then keep going to achieve
negative emissions and reduce total carbon. This is the macro level.

However, to understand whether and how things are improving on a micro level, we
need more details. A reduction in GHG emissions looks good in a report, but how
those reductions are achieved varies significantly.

As an example let’s consider the internet, which is made up of many
interconnected networks. Energy is used in the form of electricity to enable the
transmission of data across the network. There are many different telecoms
companies operating networks of varying sizes around the world. Some of these
are large enough to publish annual environmental reports, either voluntarily or
because their size triggers mandatory disclosure regulations.

Telefónica is one such company. Based in Spain, they operate large networks in
Germany, UK, France, Brazil, Peru, US and various other regions. [Their annual
report](https://www.telefonica.com/en/wp-content/uploads/sites/5/2021/07/2020-Telefonica-Consolidated-Management-Report.pdf) says
that in 2020 they consumed 6,863,728 MWh of energy, of which 4,918,373 MWh was
renewable. Total Scope 1 (directly generated) + Scope 2 (purchased energy,
market based) GHG emissions were 212,682 + 530,684 = 743,366 tCO2e.

Another company is Virgin Media. They operate primarily in the UK & Ireland
and [their annual
report](https://www.virginmedia.com/content/dam/virginmedia/dotcom/documents/corporate/VM_CARBON_DATA_TABLE_V2.pdf) says
that in 2020 their UK Scope 1 + Scope 2 (market based) emissions were 35,070
tCO2e. They don’t publish figures in energy units.

Ignoring the fact that as of 2021, Telefónica is now a part owner of Virgin
Media (this reporting is from 2020), it’s currently impossible to compare how
efficient their networks are and whether they are improving.

Telefónica operates across many more regions than Virgin, so it makes sense
their emissions are larger. However, with sufficient data that shouldn’t make
any difference to the ability to compare them. What we need is an intensity
metric – something that will give us the energy consumed per unit of work done.
In networking, this is usually [energy per unit of
data](https://doi.org/10.1109/MCOM.2014.6957153).

Telefónica actually provides this! They report the total amount of data traffic
and total amount of energy, then provide an annual figure for MWh per PB of
data. In 2015 this was 408.7 MWh/PB and in 2020 it was 78.2 MWh/PB. They don’t
provide a breakdown by region, but this is useful to see that they are improving
the energy efficiency of their network. This translates directly into emissions
reductions on a per traffic unit basis, but also on a total energy consumption
basis because such a large efficiency improvement offsets a huge growth in data
traffic.

![Graph of Telefónica's decarbonization](telefonica-carbon.png "Telefónica
reporting on emissions, data traffic and energy consumption 2015-2020
([source](https://www.telefonica.com/en/wp-content/uploads/sites/5/2021/07/2020-Telefonica-Consolidated-Management-Report.pdf)).")

Virgin Media publishes something that looks like an intensity metric, but it is
CO2e per TB of data. The calculation is from location-based emissions so is at
least linked to the region where the energy is consumed. However, even though it
is showing improvements – from 0.06 tCO2e/TB in 2014 to 0.005 tCO2e/TB in 2020,
we don’t know whether that is just inheriting the improving carbon intensity of
the grid as a whole, or if Virgin Media are investing in energy efficiency in
their network. Probably both.

Virgin Media also publish the market-based energy intensity, but this is even
less useful because it includes market measures like RECs and offsets that could
reduce that intensity to zero without improving anything on a local level.

Both companies do publish tCO2e/revenue, so we can see that on a Scope 1 + Scope
2 basis, Telefónica’s intensity is 17.26 tCO2e/€million and Virgin Media is
36.94 tCO2e/€million, but that is not particularly useful for examining their
network practices.

How would you pick a provider on the basis of their sustainability? Without an
energy per work done-based metric, you can’t be sure. Ideally you want both
energy and CO2e (which is important, but not the only aspect of sustainability).
How those CO2e reductions are achieved is also relevant – is a company actively
investing or is it just relying on system-level improvements from others? This
is another argument for [consistent and transparent reporting
standards](https://davidmytton.blog/standardizing-carbon-accounting/).
