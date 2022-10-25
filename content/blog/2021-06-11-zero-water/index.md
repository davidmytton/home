---
title: "Zero water in our data centers by 2030: mission impossible?"
date: 2021-06-11
modified: 2021-06-11
draft: false
tags: ["Data Center Water", "IT Energy"]
summary: "My remarks from a panel discussion on data center water consumption: 
Zero water in our data centers by 2030: mission impossible?"
url: zero-water-in-our-data-centers-by-2030-mission-impossible
---

On June 3rd I participated in a panel discussion on the topic of data center
water organised by [Scaleway](https://www.scaleway.com/en/). I was one of four
participants, with the other three being [Marie-Laure
Vercambre](https://fr.linkedin.com/in/marie-laure-vercambre-2353391) – Director
General of the French Water Partnership, [Arnaud de
Bermingham](https://fr.linkedin.com/in/abermingham) – President & Founder –
Scaleway, and [Manuel Mateo Goyet](https://be.linkedin.com/in/manuelmateo) –
Deputy Head of the Cloud and Software unit at the European Commission, DG
Connect.

Panel discussions are often boring, but I like the format where everyone gets
5-10 minutes to make a few remarks before going into questions from the
audience. With panel members from several stakeholder groups (industry,
government and non-profit advocacy), this ended up being a good discussion.

I’m publishing my prepared remarks below (with some links added for
sources/further reading), and you can [watch the full discussion on
YouTube](https://www.youtube.com/watch?v=jVuhUKeiMZE).

## My remarks on data center water consumption

When we think about sustainable data center and the environmental impact of IT,
most people start with energy. A lot of progress has been made over the last
decade, both in terms of the transition to renewable electricity generally, but
also specifically within the IT industry.

Large data center operators like Amazon, Google, and Microsoft, consistently hit
the top 10 list of renewable energy buyers each year. There are still challenges
about what “[100%
renewables](https://davidmytton.blog/how-can-data-centers-use-100-renewable-electricity/)”
actually means – most data center operators claiming that today are actually
just [greenwashing if they’re only using
RECs](https://davidmytton.blog/recs-cannot-be-used-to-back-claims-of-100-renewable-energy/) –
but the momentum is there.

The same cannot be said for water consumption, which I would say is a decade
behind energy in terms of understanding, transparency, and progress. However, we
have to be careful when comparing resources like energy and water because the
sustainability goals are not the same.

With energy, the goal is zero carbon, but zero water is not the right approach.
Data center water consumption is highly dependent on the region because that
dictates which cooling technologies can be used. In cooler regions, zero water
can be achieved, and should be the goal, because free air flow cooling is
possible for some, if not all, of the year. But in many hot regions, this is
simply not viable. That’s important to understand because not only is a large
part of future demand growth going to come from hot regions like Africa, South
America, India and Asia, but global temperatures are going to increase due to
global warming in general. Regions that can currently use free cooling may find
that it becomes more challenging in the future.

It is also important to understand the general context for water consumption,
because direct consumption from data centers is only a small part of global
water consumption. For example in the US, [1.7 billion litres per
day](https://www.osti.gov/servlets/purl/1372902/) is directly consumed by data
centers, but when you consider that total water consumption is over 1200 billion
litres per day, the data center footprint is insignificant.

However, that only tells part of the story because most of that focus is on
direct consumption. Over half of the daily consumption, some [500 billion litres
per day in the US](https://doi.org/10.3133/cir1441), supports thermoelectric
power consumption. Power plants generate heat using fossil fuels such as coal
and gas, or nuclear fission, to convert water into steam which rotates a
turbine, thereby generating electricity.

With the majority of generation still from fossil fuels, the transition to
renewables is important for both carbon and water intensity. Only solar and wind
energy do not involve water in
generation. [Estimates](https://www.irena.org/-/media/Files/IRENA/Agency/Publication/2015/IRENA_Water_Energy_Food_Nexus_2015.pdf) suggest
that by 2030, moving to wind and solar energy could reduce water withdrawals by
50% in the UK, 25% in the USA, Germany and Australia and 10% in India.

This means that the true data center water footprint is linked to the source of
energy, but currently this is not considered the responsibility of data center
operators, and so it doesn’t get reported.

And reporting is really limited. Data center operators are familiar with the
Power Usage Effectiveness ratio which is often used as a measure of efficiency.
A similar metric, Water Usage Effectiveness, exists, to help understand annual
site water usage. Unfortunately, less than a third of data center operators
track any water metrics and water consumption is ranked as low priority by most.
Facebook is one of the few companies operating on a global basis who report WUE,
although Google and Microsoft both publish total water consumption.
Unfortunately, you can’t actually use Facebook’s infrastructure in the same way
you can with Google and Microsoft – it’s all for their own applications. I note
that [Scaleway does also publish
WUE](https://www.scaleway.com/en/transparency/) for its 6 data centers.

Understanding the source of water is also necessary context to analyze any water
metrics. Some would argue that where water is used, the goal should not be zero
water, but zero freshwater. If water is recycled or reclaimed, its impact is not
the same as if all the water is drawn from municipal or freshwater sources.
However, this is not revealed by consumption metrics or WUE. The relative water
stress of a region is also not represented in these figures. Consumption numbers
in a region with easy access to abundant cool water take on a very different
meaning if the same numbers represented consumption in a highly water stressed
region.

All this shows how nuanced the discussion around data center water consumption
is, which explains why operators have so far been reluctant to reveal much. It’s
far easier for a layperson to understand zero carbon compared to what is needed
to understand the context of water consumption. This means much of the media
coverage around data center water focuses on highly emotive topics like access
to drinking water and pollution from water treatment. It seems the current
approach is to avoid publishing any numbers at all, so there is nothing to focus
on or report.

This reluctance is going to have to change though, because the full
environmental impact of IT is getting more and more attention. Mainstream media
is starting to report on water consumption, particularly where data centers are
the largest users in a particular region – this is something that has been in
the news recently in Holland, and local residents groups in the US have made
similar complaints in recent years. Sometimes this is about entirely new
projects, but expansion of existing sites has also been challenged as they grow
to meet the ever expanding growth of IT.

Now is the window of opportunity for data center operators. Regulation is still
limited, particularly around disclosures, but that is going to change. Data
center operators need to get ahead of reporting requirements by ensuring they
have reliable metering and a plan for water efficiency that can be implemented
over the coming years in conjunction with renewable energy projects. Renewable
energy is the model to copy because these projects are seen as positive news
stories, and data center owners have taken advantage of that to show off their
sustainability credentials. The same could be done for water. Facebook talks a
lot about its restoration projects for local watersheds and ecosystems, and
Google’s Finland data center is quite famous for being located in the snowy
north, having taken over an old mill so it can use the cold lake water.

If nothing is done then mainstream pressure will grow, and that is what
politicians respond to. I’m sure data center operators would prefer to deal with
this challenge on their own terms, but if they don’t, then politics will do it
for them. That will probably not result in favourable outcomes.

Thank you.
