---
title: "Predictions in energy and computing"
date: 2022-06-18
modified: 2022-06-18
draft: false
tags: ["IT Energy"]
summary: "Is it a good idea to make predictions about future energy consumption? 
Even mature public businesses typically only issue earnings guidance for the next 
quarter. Maybe it’s because predicting the future is hard?"
canonicalUrl: https://www.devsustainability.com/p/predictions-in-energy-and-computing
url: predictions-in-energy-and-computing
---

Is it a good idea to make predictions about future energy consumption? Or data
center energy? Or efficiency improvements? Or anything that is more than a few
years into the future?

In startups, there’s a common understanding that financial projections more than
12 months out are basically worthless. That doesn’t mean you can’t model costs –
those are under your control – but when it comes to revenue or profit figures,
customer numbers, or even more tenuous metrics like clicks, downloads, installs,
those are more uncertain the further into the future they go.

Even mature public businesses typically only issue earnings guidance for the
next quarter. Maybe it’s because predicting the future is hard?

Coming back to environmental predictions, one of the key texts I had to read at
the beginning of my Environmental Technology MSc was the 1972 publication, [The
Limits to Growth by Matthews et
al](https://en.wikipedia.org/wiki/The_Limits_to_Growth). This uses simulations
and models to predict the future based on the trends of the time, with the
famous prediction:

> The basic behavior mode of the world system is exponential growth of
> population and capital, followed by collapse. As we have shown in the model
> runs presented here, this behavior mode occurs if we assume no change in the
> present system or if we assume any number of technological changes in the
> system.
>
> <cite>[The Limits to Growth](https://en.wikipedia.org/wiki/The_Limits_to_Growth),
> Matthews et al.</cite>

I found this interesting because, of course, my reading it many decades after it
was published obviously meant that the world had not ended! Technological change
has indeed been able to make a huge difference to the outcomes of “business as
usual”, not least the invention of widespread computer technology.

The Limits to Growth is not even the most famous of these types of fundamental
errors of prediction. Malthusianism must surely take that title, but they are
all in the same category. It’s worth comparing to the IPCC reports and UK
Government Net Zero plans because The Limits to Growth said that technology
change would have no impact on stopping the inevitable collapse, whereas modern
reports say that technology change will be crucial to avoiding those problems.

That is not to say that we can just continue to do as we have in the past. We
can’t just keep burning fossil fuels, or failing to measure water consumption in
areas of water stress, or ignoring the poor working conditions where key
minerals are being mined. But [making dire predictions so far into the
future](https://davidmytton.blog/extrapolation-of-data-center-energy-estimates/) that
they lack credibility [is not
helpful](https://rogerpielkejr.substack.com/p/the-unstoppable-momentum-of-outdated).

Extrapolation only works if all variables remain constant. Maybe it’s possible
to adjust for certain changes here and there, but it’s difficult enough to model
the past behavior of complex systems. Making predictions more than a year or two
into the future is almost impossible, even when you don’t have unexpected events
like a pandemic to deal with.

Will Moore’s Law finally end? [We thought that was
happening](https://davidmytton.blog/paper-notes-what-will-drive-computer-performance-after-moores-law/),
then the industry started shifting to a completely different CPU architecture.
ARM chips [on the
desktop](https://www.apple.com/newsroom/2022/06/apple-unveils-m2-with-breakthrough-performance-and-capabilities/) and [in
the data
center](https://perspectives.mvdirona.com/2022/05/graviton3-ec2-c7g-general-availability/) are
growing rapidly. [Offloading software development to the
cloud](https://dx.tips/the-end-of-localhost) will improve efficiency.
Centralization is good for taking advantage of economies of scale, but moving
workloads closer to users will also have benefits. Processing data on a single
CPU might be reaching the end of the innovation cycle, but we’ve only just
started to rearchitect and split workloads to specialist environments. Can you
predict how that is going to play out?

This presents a challenge for those working on large infrastructure projects,
particularly energy systems that have lead times measured in years, such as
building new power plants or constructing transmission lines. Organizations like
National Grid produce [Future Energy
Scenarios](https://www.nationalgrideso.com/future-energy/future-energy-scenarios) to
help them plan how the energy grid will need to change over the coming years.
Building out too much capacity means wasted resources, but failing to deal with
unexpected demand might be worse – [delayed
projects](https://www.economist.com/britain/2022/06/02/britains-overstretched-electricity-grid-is-delaying-housing-projects),
brownouts, or system failures.

There is no easy answer, so I try to remain skeptical of predictions. When I see
a new estimate, I first think about whether the prediction fits the general
direction I was expecting. Ranges are helpful because an exact number is rarely
needed, so long as it is within a reasonable range. Anything that is an order of
magnitude different from where we are today, or is going in a completely
different direction than expected, is where I dig into the details.

The near future (a few years) tends to be quite similar to today. The far future
tends to be very different, so is impossible (and pointless) to predict. It’s
the mid-range that causes all the problems.
