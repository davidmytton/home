---
title: "Approaches to calculating website energy and carbon"
date: 2022-07-14
modified: 2022-07-14
draft: false
tags: ["IT Energy", "Website Energy", "Network Energy"]
summary: "Website carbon calculators are not very accurate, especially if they 
only use data transfer as the metric."
url: approaches-to-calculating-network-website-energy-and-carbon
---

It’s common to see carbon calculations for websites and other network services
using data transfer as the unit of work. This is multiplied by an energy
intensity figure to get the energy consumed.

For 2020 calculations, a commonly used energy intensity figure is 0.0065 kWh/GB
taken from [Aslan et al](https://doi.org/10.1111/jiec.12630) (or 0.06 kWh/GB if
you don’t read the paper and fail to realize the 2015 figure in the abstract is
projected to fall by half every 2 years). Assuming a website total download size
of 1MB (0.001GB), this would be 0.001 \* 0.0065 = 0.0000065 kWh.

Carbon emissions are then calculated using a carbon factor, usually one from the
local government wherever the data center is located.

However, this method has a lot of assumptions:

- Is all of that data downloaded on every page load? How much is cached by the
  browser?

- Are there any CDNs involved? Are they moving data from a centralized origin
  and then caching it?

- Is any processing happening on the server side? What about in the browser,
  such as executing JS or decoding video?

- The intensity figure is an average – it doesn’t capture differences between
  high and low data volume applications such as web browsing vs video
  streaming.

- What about on mobile devices? The figures from Aslan et al only refer to
  fixed-line networks in countries with modern, advanced infrastructure.
  They’re not valid on a global basis (another common error).

So you may end up with a figure, but is it useful for taking action in any way
that actually makes a difference?

## Allocational vs power model approach

The model described above is commonly used to allocate fixed resources to a
user, service, or unit of work (GB transferred in this case). It’s useful if you
already know the total energy consumption and need to allocate it for reporting
because the averages can be used to estimate the past.

However, that’s not how networks actually work. The infrastructure in use when
you visit a website has already been deployed, the network equipment is already
running, and the capacity has already been fixed based on expected peak load.
The network is always-on and is always drawing power. Unlike servers, which over
time have been improving their dynamic range – [meaning their power consumption
is more proportional to
load](https://davidmytton.blog/how-much-energy-do-data-centers-use/) – network
energy consumption has a baseline and varies by only small amounts based on
traffic volume.

There is a baseline level of power consumption and this varies by small amounts
depending on the activity e.g. video streaming for an hour or two, but the
overall energy consumption does not change that much. This is known as the power
model approach, described in [a 2020 conference paper by
Malmodin](https://online.electronicsgoesgreen.org/wp-content/uploads/2020/10/Proceedings_EGG2020_v2.pdf) and
explained in detail in [a 2021 Carbon Trust report on video
streaming](https://prod-drupal-files.storage.googleapis.com/documents/resource/public/Carbon-impact-of-video-streaming.pdf).

![Graph of power and data over time](power-data-power-time.png "Power/data and power/time over 24hrs for fixed-line broadband. This hows how power consumption increases by only 0.2W during a 1 hour Netflix session. **Source:** [Malmodin, J. (2020)](https://online.electronicsgoesgreen.org/wp-content/uploads/2020/10/Proceedings_EGG2020_v2.pdf).")

The result is that short-term network energy consumption is not directly
proportional to data transferred. We can see this from network operator annual
reports which show large increases in data traffic, but falling energy intensity
figures.

Over longer time periods, increases in traffic do result in an increase in total
energy consumption because network capacity is expanded. Networks need to cope
with peak load and include redundancy. But that may be offset by newer, more
efficient networking equipment, and the intensity figures fall because the
increase in traffic outweighs the increase in total energy.

Both approaches have their uses. The allocational approach is much more well
known and understood, but is probably only useful for backwards looking
reporting. It can’t reflect changes in page size, or video quality settings, for
example. The power model approach is much more reflective of how networks
actually work, but it’s quite new and the research to-date only discusses
specific networks with particular characteristics which are difficult to
generalize.

![Graph of energy use and network data flows](energy-network-data-graph.png "Annual energy use and network data flows for two large network providers, expressed as an index relative to 2016 = 1.0. **Source:** [Koomey & Masanet, 2021](https://dx.doi.org/10.1016/j.joule.2021.05.007).")

## How accurate are website carbon calculators?

Website carbon calculators are not very accurate, especially if they only use
data transfer as the metric. Average values can’t represent the variety of
applications which means they can’t be used for comparisons.

Many calculators make basic errors, taking figures from old academic papers or
reports based on papers which are outdated or have [suspicious
methodologies](https://davidmytton.blog/extrapolation-of-data-center-energy-estimates/).
Always check how the calculations are performed and the sources for the energy
intensity figure – has it been correctly adjusted for time? Do they caveat the
calculations with anything mentioned above?

The calculators from the cloud providers are more useful because they work off
real data…I assume. They should, because Amazon, Google and Microsoft all know
how much energy their infrastructure consumes so they can allocate it across
their customers and services. [This is useful for
reporting](https://davidmytton.blog/cloud-emissions-transparency-stage-1-completed-what-next/),
but their methodologies are less than transparent so it’s hard to be sure.

However, I’d bet they are much more accurate than anything else. Trying to
calculate the carbon footprint of a website based on data transfer without
knowing the actual energy consumption of the underlying resources is not going
to produce useful results. Focusing on page performance [using something like
Google’s Lighthouse](https://web.dev/measure/) (which includes reducing download
sizes) is a better use of time.
