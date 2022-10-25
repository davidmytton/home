---
title: "Sustainable computing – where to focus?"
date: 2020-12-07
modified: 2020-12-07
draft: false
tags: ["IT Energy", "Data Center Energy"]
summary: "Progress in renewable energy has pushed IT carbon footprints down, 
revealing how much more work is needed in manufacturing."
url: sustainable-computing-where-to-focus
---

Climate change is the biggest and most important long-term challenge we face.
Everything about tackling this problem is focused on carbon dioxide
([equivalent](https://en.wikipedia.org/wiki/Global_warming_potential)) emissions
and how we reach net zero, or ideally [net
negative](https://www.iea.org/commentaries/going-carbon-negative-what-are-the-technology-options).

The underlying story in [the Dispatches documentary episode I was recently
interviewed
for](https://www.channel4.com/programmes/dispatches/on-demand/71182-001) was
that the tech industry uses a lot of energy, which is generated from sources
with a high carbon intensity. Such analysis typically focuses on the use-stage
energy, usually electricity, because renewables still make up a minority of
global primary energy demand. [As of
2019](https://www.iea.org/reports/energy-technology-perspectives-2020/clean-energy-technologies-the-state-of-play#abstract),
wind power accounted for 5% of global power supply, solar 2.5%, and the rest is
either natural gas, oil, or coal, with a small amount of biomass and nuclear.

Framing the problem in this way [allows the media to position big tech as part
of the
problem](https://stratechery.com/2020/twitter-responsibility-and-accountability/) because
they run the infrastructure behind an increasing proportion of the services we
all use. Energy is a major component of this environmental impact, and is one of
the larger causes of the carbon emissions contributing to climate change.
However, it is not the only environmental impact of computing and there is a
risk of tunnel vision if we only focus on carbon.

Moving from coal power generation to wind power not only reduces the carbon
intensity of the electricity generated, but it also reduces air pollution,
decreases water intensity, and removes the need for mining. These are all
important environmental improvements, but they have become secondary with the
focus on carbon.

## Energy and sustainable computing

Data centres get significant focus in discussions about sustainable computing
because it’s easy to pick on an industry that is growing rapidly, [consuming a
lot of energy](https://www.nature.com/articles/d41586-018-06610-y), and
where [the biggest player (Amazon) lacks
transparency](https://doi.org/10.1186/s13677-020-00185-8). This seems intuitive
because we all get an electricity bill and can link charging our laptop or phone
to what we pay each month. However, the tech industry has made significant
progress in decarbonising the infrastructure it owns – mostly data centres. When
it comes to the big cloud providers, this narrative is becoming outdated and at
least [Google and Microsoft are fighting over who has the greenest
cloud](https://davidmytton.blog/fighting-over-who-has-the-greenest-public-cloud/).

Yet despite this progress in the data centre world, there remain some major
areas that need work. Whilst using public cloud in super efficient hyperscale
data centres might be standard practice for modern organisations and
startups, [there are questions around how rapidly workloads are migrating from
older data
centres](https://journal.uptimeinstitute.com/it-venue-selection-when-choosing-in-house-or-outsource/).

Small data centres are another area of uncertainty – with just a few servers,
they still [make up 40% of all data centres in the
US](https://escholarship.org/uc/item/8dh8j3kq). These facilities are very
inefficient and consume 13TWh of energy annually. This is between 2.5-6% of
total data centre energy consumption ([depending on which estimate you
use](https://davidmytton.blog/how-much-energy-do-data-centers-use/)) but the
carbon impact is still meaningful.

Then there’s everything outside of what the public cloud providers own, but that
is still within their supply chain. Google and Microsoft both provide detailed
environmental reporting for their own data centres but what about everything
else? For example, [Google publishes
figures](https://www.google.com/about/datacenters/efficiency/) about 17 of its
data centres but note how many locations are missing. Where are the detailed
about its London cloud region? Or Tokyo? Either these are outside the scope of
“large scale” and/or “campuses with at least twelve months of data”, or they are
being excluded because Google doesn’t own them. Perhaps Google is leasing space
in a colo provider instead, thereby [outsourcing its emissions to a third
party](https://doi.org/10.1038/s41558-020-0837-6).

What about the network? When you stream a video from YouTube, you are
responsible for the energy consumption of your laptop and Google is responsible
for the energy consumption of its data centre, but what about the infrastructure
inbetween? You have a home internet provider but that connects through multiple
networks before it reaches Google. [Network energy efficiency improves by 50%
every 2 years](https://doi.org/10.1111/jiec.12630), but even so data
transmission networks [consumed 250 TWh in
2019](https://www.iea.org/reports/data-centres-and-data-transmission-networks),
more than data centres. Global internet traffic increased by 40% between Feb and
Apr 2020 due to the Coronavirus lockdowns. This is the subject of an upcoming
paper I expect to publish next year.

![Graph to show estimates for electricity intensity for the transmission
network](aslan-network-energy-decline.png "Graph to show estimates for
electricity intensity for the transmission network system from [Aslan, et al
(2018)](https://doi.org/10.1111/jiec.12630).")

## Materials and sustainable computing

The big players like Microsoft, Google, and Facebook, have been successful in
their transition to powering their data centres with renewable electricity. This
means that even as data centre energy consumption increases, the carbon
intensity decreases.

![Graph of the carbon footprint of purchased energy](energy-carbon.png "Although the energy consumption of Facebook’s Prineville data centre increased between 2013 and 2019, its operational carbon output decreased because of renewable-energy purchases. From [Gupta, et al (2020)](https://arxiv.org/abs/2011.02839v1).")

This is great progress, but computing is much more than just energy. There
is [the water required to generate that energy, and cool data
centres](https://davidmytton.blog/how-much-water-do-data-centers-use/), but also
all the materials needed to manufacture, transport, and recycle.

![Hardware lifecycle illustration](hardware-lifecycle.png "The hardware life cycle includes production, transport, use, and end-of-life processing. Opex-related (operational) carbon emissions are based on use; capex-related emissions results are from aggregating production/manufacturing, transport, and end-of-life processing. From [Gupta, et al (2020)](https://arxiv.org/abs/2011.02839v1)")

Behavioural changes are often what people focus on when thinking about how they
can combat climate change. Eating less meat is a good idea. Cycling is better
than driving. But these types of interventions get too much attention. Most
people are not going to shift their behaviour. They are going to continue
listening to music using videos on YouTube [despite it using significantly more
energy than audio-only streaming](https://doi.org/10.1145/3290605.3300627). Or
accept the Netflix default of streaming in 4k quality even if they don’t have a
4k TV or laptop. When it comes to sustainable computing, the best way to reduce
your impact on the environment is to not buy a new laptop or phone. If you buy a
new iPhone 12, [only 14% of the carbon footprint is in using
it](https://www.apple.com/euro/environment/pdf/a/generic/products/iphone/iPhone_12_PER_Oct2020.pdf).
Whether you charge it using renewable electricity hardly matters when 83% of the
carbon goes into the manufacturing.

The material aspects of computing need more attention – mining rare earth
metals, chemical processes to produce circuit boards, manufacturing of
semiconductors, construction of factories and other facilities like data
centres, mass production of electrical components, wires, LCD panels, printing
packaging, transport around the world, recycling methods and reclaiming used
materials. These are key components of detailed Lifecycle Assessments, yet we
rarely have sufficient insight into the supply-chains of major electronics and
computing manufacturers.

This is why more pressure needs to be placed on the organisations we transact
with. [Apple is a leader](https://www.apple.com/environment/) with their
commitment to using 100% renewable electricity by 2030 and the efforts it has
made in using recycled materials. But they get a big FAIL when it comes to
repairability. It’s better to be able to buy a small replacement part than to
have to ship your laptop off to a workshop, which due to how Apple designs its
systems often requires replacing many large components.

We can signup with an electricity company at home that contracts to provide us
with renewable electricity, and we know that Google owned data centres are
powered by renewable electricity ([on an annual
basis](https://davidmytton.blog/how-can-data-centers-use-100-renewable-electricity/)),
but everything else involved with streaming of a YouTube video remains a black
box. We are only at the beginning of understanding the true environmental impact
of computing.

## Sustainable computing – where to focus?

The transition to renewables is happening. [Renewables will
account](https://www.iea.org/reports/renewables-2020) for almost 90% of the
increase in global total power capacity in 2020, and this will accelerate in 2021. There is still a long way to go but [the economics of wind (and solar)
have been proven](https://doi.org/10.1038/s41560-020-0661-2).

Data centre energy is following this trend. Microsoft and Google are making the
most progress but Amazon has also pledged to follow them. Colo and traditional
data centres need to work a lot harder, and there has been little focus on the
networks connecting the user to the services they use.

Progress in renewable energy has pushed IT carbon footprints down, particularly
in the use-stage, revealing how much more work is needed in manufacturing. More
attention needs to be paid to the rest of the supply chain. Data centre water
consumption is a grey area, and lifecycle analysis needs to expand from just
energy to examine the full environmental footprint of computing. There is a lot
more research to be done!
