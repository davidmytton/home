---
title: "Zoom, video conferencing, energy, and emissions"
date: 2020-11-16
modified: 2022-07-14
draft: false
tags: ["Data Center Energy", "IT Energy", "Network Energy"]
summary: "It is obvious that Zoom is better for the environment than flying but 
what about vs driving an EV or public transport? The problem is we can't 
be sure."
url: zoom-video-conferencing-energy-and-emissions
---

I was recently invited to discuss the topic of [IT
energy](https://davidmytton.blog/category/data-center-energy/) and the [lack of
transparency](https://davidmytton.blog/sustainability-doesnt-work-without-transparency/) in
an episode of the documentary
series, [Dispatches](https://www.channel4.com/programmes/dispatches), which was
broadcast on Channel 4 in the UK at 8pm on 16 November 2020 ([available online
here](https://www.channel4.com/programmes/online-habits-killing-the-planet-dispatches)).
One of the topics I was asked about was video conferencing, and Zoom in
particular.

Although claims about how green video conferencing is compared to travelling to
a meeting are not new, the sudden growth of online meetings caused by the
Coronavirus pandemic has brought this into the mainstream.

It intuitively makes sense that speaking to someone over a Zoom video conference
is better for the environment than flying to meet in person. The problem with
intuitive assumptions is that they often work out to be more complex than you
think.

For example, charging shoppers for plastic bags [has been very successful in
reducing the number of plastic bags
used](https://www.gov.uk/government/news/plastic-bag-sales-in-big-seven-supermarkets-down-86-since-5p-charge).
However, whether that is better for the environment depends on what they are
replaced with and how many times that replacement is used.

[A lifecycle analysis from the Danish
government](https://www2.mst.dk/udgiv/publications/2018/02/978-87-93614-73-4.pdf) shows
that compared to a standard plastic bag, an unbleached paper bag is better when
considering impacts on climate change, but it would need to be reused 43 times
to have a positive impact on all environmental factors. This is because
“environment” means many things: pollution, ozone depletion, causes of human
cancer, acidification of freshwater, resource depletion, and others. The worst
thing you can do is replace a plastic bag with organic cotton which requires
20,000 reuses before it is better for the environment.

In the context of video conferencing, it is safe to assume that arranging a Zoom
call is better than flying business class from London to New York, but is it
better than both participants walking to a cafe in the city they both already
live in? Maybe someone was going to drive their EV to the office. What about if
you have many participants all over the world? How about if some connect via 4G
vs others on a laptop?

To go a bit deeper than is possible in a TV documentary, this post attempts some
rough calculations to try and get an answer to these questions.

## What does Zoom say about their emissions?

Not much. They treat their environmental impact as marketing.

[One blog post from
2019](https://blog.zoom.us/how-video-meetings-are-helping-reduce-environmental-impact-infographic/) explains
how an example Zoom call would generate 4kgCO2 vs 687kgCO2 flying from New York
to San Francisco for the equivalent meeting (the actual video meeting was only
0.0045kgCO2, the rest being commuting to the office).

Although the blog post mentions “University of Pennsylvania” as the source of
this, I could not find how they calculated that figure. The other source
mentioned is [a 2009 report from the
WWF](https://wwf.panda.org/?160342/IT-solutions-offer-cost-and-climate-benefits) which
does not provide a specific number, and is 10 years out of date.

[The other
blog](https://blog.zoom.us/zoom-recognizes-uber-hp-genpact-autodesk-reduced-co2-emissions/) post
states that Zoom’s top 10 customers avoided over 685k metric tons of CO2 in 90
days. This is useless unless you know what they actually emitted.

If Zoom is so great for the environment vs the alternatives, you might expect
them to provide numbers to prove it.

## Calculating Zoom’s emissions

In the absence of Zoom providing any data about the emissions of a video call,
we can perform some basic calculations ourselves.

[Zoom recommends](https://support.zoom.us/hc/en-us/articles/201362023) the
following bandwidth requirements:

- For 1:1 video calling:
  - 600kbps (up/down) for high-quality video
  - 1.2Mbps (up/down) for 720p HD video
  - Receiving 1080p HD video requires 1.8Mbps (up/down)
  - Sending 1080p HD video requires 1.8Mbps (up/down)
- For group video calling:
  - 800kbps/1.0 Mbps (up/down) for high-quality video
  - For gallery view and/or 720p HD video: 1.5Mbps/1.5Mbps (up/down)
  - Receiving 1080p HD video requires 2.5Mbps (up/down)
  - Sending 1080p HD video requires 3.0Mbps (up/down)

For 2019, the electricity intensity of fixed-line internet data transmission is
0.015kWh/GB (extrapolating the 2015 figure from [Aslan et al,
2018](https://doi.org/10.1111/jiec.12630) to 2019), so we need to convert these
figures from bits into gigabytes:

- For 1:1 video calling for 1 hour:
  - HQ = `0.000075GB/s = 0.27GB/hr * 2 (up/down) = 0.54GB`.
  - HD 720p = `0.00015GB/s = 0.54GB/hr * 2 (up/down) = 1.08GB`.
  - HD 1080p = `0.000225GB/s = 0.81GB/hr * 2 (up/down) = 1.62GB`.
- For group video calling for 1 hour:
  - HQ = `0.0001GB/s + 0.000125GB/s = 0.36GB/hr + 0.45GB/hr = 0.81GB`.
  - Gallery view and/or HD 720p = `0.0001875GB/s = 0.675/hr * 2 (up/down) = 1.35GB`.
  - HD 1080p = `0.0003125GB/s + 0.000375GB/s = 1.125GB/hr + 1.35GB/hr = 2.475GB`.

These figures are per participant which means that a 1 hour 1:1 conversation
could generate `1.08 – 3.24GB` of network traffic using `0.0162 – 0.0486 kWh` of
electricity.

For a group call between 6 people, that could generate `4.86 – 14.85GB` of traffic
and use `0.0729 – 0.22275 kWh` of electricity.

At the upper limit, Zoom can support up to 1,000 participants ([and has gone up
to 100,000 in special
situations](https://www.cnet.com/news/estimated-100000-join-massive-zoom-event-honoring-late-orthodox-rabbi-menachem-m-schneerson/)),
which could generate a range of `810 – 2,475GB` of network traffic using `12.15 – 37.125 kWh` of electricity.

Now we know the electricity consumed, we can calculate the emissions. This is
where it starts to get more complex because the emissions factor depends on the
grid mix in each location. A very simple calculation could assume that all
network transmission remains within a single country.

For example, a 1:1 HD 1080p video meeting of 1 hour between two people would
require `3.24GB` of bandwidth, consuming `0.0486 kWh` of electricity. [The 2019 UK
electricity emissions
factor](https://www.gov.uk/government/publications/greenhouse-gas-reporting-conversion-factors-2019) is
`0.25358 kgCO2 per kWh`, so the CO2 emissions for this call are `0.012 kgCO2`.

If this happened in the US between two people in New York, [the emissions factor
is similar to the UK at 0.28839 kgCO2 per
kWh](https://www.epa.gov/sites/production/files/2018-03/documents/emission-factors_mar_2018_0.pdf) but
if it was between two people in Chicago, that would be `0.56191 kgCO2 per kWh`.
Location matters.

## Big assumption – are data transfer and network energy correlated?

_Update July 2022:_ The main assumption from the above calculation is that
network energy and data transfer are correlated i.e. the more data transferred,
the greater the energy consumption. A lot of academic literature uses this
model, which is why you can find kWh/GB figures in the likes of [Aslan et al,
2018](https://doi.org/10.1111/jiec.12630) and [the Carbon Trust Carbon impact of
video streaming
report](https://prod-drupal-files.storage.googleapis.com/documents/resource/public/Carbon-impact-of-video-streaming.pdf).
But is this accurate? Simple extrapolations generally result
in [absurd](https://davidmytton.blog/extrapolation-of-data-center-energy-estimates/) numbers.

Since writing this blog post in 2020, a different model of assessing energy
intensity of applications which use the network has emerged depending on whether
you are measuring the instantaneous increase in power consumption caused by that
consumption, or whether you are allocating energy for reporting purposes. These
approaches are discussed in detail in [the Carbon Trust Carbon
report](https://prod-drupal-files.storage.googleapis.com/documents/resource/public/Carbon-impact-of-video-streaming.pdf) and
at a high level [in a 2021 article in
Joule](https://dx.doi.org/10.1016/j.joule.2021.05.007). [I wrote also a post
about
it](https://davidmytton.blog/approaches-to-calculating-network-website-energy-and-carbon/).
More work is needed here.

## What is missing from the calculation?

Note how we are only talking about the network energy consumption between
participants in a single location. This is the most basic situation, and things
quickly become more complex:

- What about people in different countries? You need to apply a local emissions
  factor for each person.
- What about the type of network they are connected to? The figure of
  0.015kWh/GB applies only to fixed-line networks. Mobile connectivity in 2020
  uses 0.1kWh/GB ([Pihkola et al., 2018](https://doi.org/10.3390/su10072494)).
- What about their devices? We have only calculated the energy of the network.
  The energy used by the computer, the display, and the phone or router they are
  connected to is excluded
- What about [the data
  center](https://davidmytton.blog/how-much-energy-do-data-centers-use/)? Zoom
  does not publish any figures about its own infrastructure and how much energy
  that consumes. [Zoom primarily uses Amazon Web
  Services](https://www.datacenterdynamics.com/en/news/most-zoom-runs-aws-not-oracle-says-aws/) for
  their infrastructure, but they also use Oracle and [9 Equinix data
  centers](https://www.prnewswire.com/news-releases/zoom-expands-with-equinix-to-future-proof-and-scale-its-video-first-cloud-native-architecture-300962299.html). [Oracle
  reports](https://www.oracle.com/customers/zoom.html) that Zoom are
  transferring up to 7 petabytes of data per day. Using the 0.015kWh/GB figure
  above suggests that would consume 105,000 kWh of electricity every day just
  for a small part of their network traffic.
- What about all the servers? [Zoom
  said](https://www.datacenterdynamics.com/en/news/most-zoom-runs-aws-not-oracle-says-aws/) they
  were adding 5000 – 6000 new servers per day on AWS to help during COVID. That
  is a lot. We don’t know where those servers are, how long they run for, or
  what spec they are.

## How does this compare to travelling?

As usual, it depends. [In the
UK](https://www.gov.uk/government/publications/greenhouse-gas-reporting-conversion-factors-2019),
a medium sized battery electric vehicle generates 0.05275 kgCO2 per km travelled
compared to a medium petrol car which generates 0.19158 kgCO2 per km travelled.
A round trip economy flight from London Heathrow to New York JFK [generates
670.9
kgCO2](https://www.icao.int/environmental-protection/CarbonOffset/Pages/default.aspx).

We can easily find an example where there are significantly more emissions than
a video call, but we could just as easily pick an example to show the opposite
e.g. by walking to a local cafe to meet someone who also walked there.

> If the travel distances from our case study are halved, such that the domestic
> participant travels 500 km and the international participant travels 2500 km,
> the overall energy contribution from the in-person meeting will fall by half
> to give 10.6 GJ (plane), 8.7 GJ (train) and 10 GJ (car). The travel distances
> will need to be shortened 15-fold (e.g. to a miniscule 67 km for the domestic
> participant and 333 km for the international participant) to reduce the
> lifecycle energy cost of the in-person meeting such that it matches the cost
> of videoconferencing. However, these results show that there are certain
> conditions in which having an in-person meeting is still better than
> videoconferencing environmentally, especially for high-end telepresences that
> have a higher energy profile.
>
> <cite>[Ong, Moors & Sivaraman,
> 2014](https://doi.org/10.1016/j.comcom.2014.02.009).</cite>

The form of transport being compared makes a big difference:

> The potential of teleworking for reducing transportation energy use and GHG
> emissions also depends on the form of transportation it is replacing. In
> regions with a high proportion of walking, cycling, and public transportation,
> the benefit of teleworking is significantly less than in sprawling cities
> where commuters primarily rely on personal automobiles and with bad
> congestion.
>
> <cite>[O’Brien & Yazdani Aliabadi,
> 2020](https://doi.org/10.1016/j.enbuild.2020.110298).</cite>

You would need to have over 55,000 hours of 1:1 HD 1080p video meetings to equal
the same emissions generated as a return flight from London to New York (670.9
kgCO2 for the flight / 0.012 kgCO2 for the video call).

But if you and your colleague drove your EVs 10km into a local office (`10 km * 2 to/from journey* 2 people * 0.05275 kgCO2 = 2.11 kgCO2`) and worked together
for an 8 hour day, this would be equivalent to 21 hours of HD 1080p video
meetings (`2.11 kgCO2 for the journey / (0.012 kgCO2 for 1 hour video call * 8 hours` ).

These numbers get us to the point where the uncertainty over the remainder of
non-network-transmission emissions from a Zoom call could make a difference.
When you add in Zoom’s data center and the electricity consumption from your
computer or phone, it could be that using the London Underground to commute into
the office for a day of meetings is better (or similar to) using Zoom.

![Graph of energy by distance for meetings](energy-distance.jpg "Energy curve
for all meeting modes as the aggregated travel distance is varied, from [Ong,
Moors & Sivaraman, 2014](https://doi.org/10.1016/j.comcom.2014.02.009).")

Understanding the total impact is even more challenging. Rebound effects of more
frequently working from home mean an impact assessment is difficult. [O’Brien &
Yazdani Aliabadi
(2020)](https://doi.org/10.1016/j.enbuild.2020.110298) discusses effects such
as:

- The increased frequency and/or distance of non-work trips.
- Many commuters carry out errands during their commute, making them more
  efficient.
- Telecommuters can avoid rush hour so when they do travel, they may travel
  further because it is more enjoyable.
- Tendency to live further from amenities means that those trips are more likely
  to be taken by personal car, rather than more sustainable means.
- Teleworkers tend to drive alone rather than take transit on non-telecommuting
  days.
- Telecommuting makes vehicles more available to other household members to use.
- A reduction in commuting costs (e.g., multiple household cars) frees up funds
  for other potentially energy-intensive purchases (e.g., larger house,
  international vacations).

These factors are of course outside the control of Zoom, but highlight the
complex factors that make such claims more challenging to accurately assess.

## What should Zoom do about this?

It is obvious that video conferencing is better for the environment in general
than flying. It is probably better than driving a petrol or diesel car, may be
better than an EV, but might not be better than public transport. However, we
can’t say much more than that. Zoom could help in the following ways:

1. Provide annual reports on the total amount of energy consumed across the
   entire operations of the company.
2. Provide users with reporting on the total amount of data transmitted by their
   Zoom client (ideally broken down by client type e.g. x GB from the desktop
   client and y GB from the mobile client). If participants are members of a
   company account, this could be aggregated for all users.
3. [Follow the same approach as Google and
   Microsoft](https://davidmytton.blog/how-can-data-centers-use-100-renewable-electricity/) in
   working towards offsets + 100% renewable matching + 100% renewable sourcing
   for their data centers.
   1. If they do this, users only need be concerned with the emissions from
      their own data transfer because Zoom will be mitigating the data center
      emissions.
   2. If they do not do this, Zoom should provide an energy intensity figure in
      kWh/GB of data transmitted (or minute of video streaming) to consider all
      the electricity consumed in the network and their data centers. Users (or
      their organisation on their behalf) can then calculate the emissions from
      their video streaming, and mitigate it themselves.

Nothing has zero emissions. Zoom compares favourably to the alternatives such as
flying. That is great progress but it isn’t sufficient. Where they should be
embarrassed is that they don’t release enough for us prove what they claim.
Otherwise it all just looks like greenwashing.
