---
title: "Paper notes – What will drive computer performance after Moore’s law?"
date: 2021-08-27
modified: 2021-08-27
draft: false
tags: ["Paper Notes", "IT Energy", "Hardware", "Energy Efficiency"]
summary: "What will drive computer performance after Moore’s law? Will 
programmers need to focus on performance or can ARM chips and the cloud save 
us?"
url: paper-notes-what-will-drive-computer-performance-after-moores-law
---

### Paper

Leiserson, C.E., Thompson, N.C., Emer, J.S., Kuszmaul, B.C., et al. (2020)
There’s plenty of room at the Top: What will drive computer performance after
Moore’s law? *Science*. 368 (6495), eaam9744. Available from:
doi: [10.1126/science.aam9744](https://doi.org/10.1126/science.aam9744).

### Abstract

> The miniaturization of semiconductor transistors has driven the growth in
> computer performance for more than 50 years. As miniaturization approaches its
> limits, bringing an end to Moore’s law, performance gains will need to come
> from software, algorithms, and hardware. We refer to these technologies as the
> “Top” of the computing stack to distinguish them from the traditional
> technologies at the “Bottom”: semiconductor physics and silicon-fabrication
> technology. In the post-Moore era, the Top will provide substantial
> performance gains, but these gains will be opportunistic, uneven, and
> sporadic, and they will suffer from the law of diminishing returns. Big system
> components offer a promising context for tackling the challenges of working at
> the Top.

### Notes

- Over the past 50 years, computer processing performance has roughly doubled
  every 2 years because of the ability to miniaturize chip transistors. The
  smaller the transistor, the more can be fit onto a single chip.
- As we reach the physical limits of atoms, the industry has shifted to
  increasing the number of chip cores as well as specializing those cores. GPUs
  are a good example of chips specializing in graphics processing, which turns
  out to have also helped parallelizable processing like training machine
  learning models. Apple’s M1 chip is another example where it has multiple
  cores focused on specific tasks. For example, the M1 MacBook Air has an 8 core
  CPU made up of 4 performance cores and 4 high efficiency cores, plus an 8 core
  GPU for graphics processing.
- All this means that programmers have not had to focus as much on performance
  except at the extremes in low-resource systems such as embedded chips, or at
  the very large scale where performance makes a big difference to
  transactions/queries/requests per second.
- Now Moore’s Law is coming to an end, the predictions are that programmers are
  going to have to start thinking about performance more of the time.
- This is important from a sustainable computing perspective because computer
  hardware, especially in data centers, is notoriously underutilized. The best
  scenarios in hyperscale cloud environments can reach around 50% utilization,
  but most systems operate at significantly less than that. Power
  proportionality – how much power is consumed when a system is idle vs under
  load – has improved over the last decade so idle servers are consuming less
  power, but it is still not directly proportional.
- This paper discusses the concept of “performance engineering” where there is a
  focus on performance improvements rather than writing simple but naive code.
  They use an example where a 4-line matrix calculation written in Python ported
  to C results in a x47 performance improvement. This can be improved by x62,806
  by optimizing the code to take advantage of parallel loops, vectorization and
  then eventually Intel CPU specific functionality.
- One of the major points of the paper is that programmers have traded ease of
  use of the language for performance because the goal has been to reduce the
  time needed to write code rather than dealing with performance in production.
  They argue there is lots of room at “the top” for programmers to work closer
  with the hardware to produce more efficient code.

![Illustration of performance agins after Moore's law](performance-gains-top.png "Performance gains after Moore’s law ends. In the post-Moore era, improvements
in computing power will increasingly come from technologies at the “Top” of the
computing stack, not from those at the “Bottom”, reversing the historical trend.
From [Leiserson, C.E., Thompson, N.C., Emer, J.S., Kuszmaul, B.C., et
al](https://doi.org/10.1126/science.aam9744).")

- The paper also discusses how algorithmic efficiency improvements can result in
  performance improvements that match the gains made through hardware
  improvements. The authors encourage more research into algorithms and how they
  can be improved.
- This observation comes from the world of computer science where algorithms are
  a core part of the science. I wonder how much this is relevant to industry.
  Algorithms are used in many systems-level applications in operating systems as
  well as for some of the core web applications such as search and routing
  directions for maps and navigation, but how representative are these of what
  most programmers build? How many of the algorithms published by computer
  scientists are actually used in the applications most programmers write?
- To what extent is computer science as an academic discipline relevant to the
  majority of the work that happens in the real world?
- The paper concludes by mentioning a number of technologies at “the bottom”
  which could push the end of Moore’s Law further – 3D stacking, quantum
  computing, photonics, graphene chips. However, they missed two technologies
  that are here today:
  - **ARM Chips** – the Apple M1 chip shows what can be achieved if the OS is
    optimized to work with a set of highly efficient and performant ARM chips,
    and also achieves amazing energy efficiency. I expect we’ll see even more
    improvements as Apple continues its R&D and releases its next generation.
  - **Cloud Computing** – programmers have been able to take advantage of the
    improvement in underlying hardware. Now that is coming to an end, will they
    instead be able to take advantage of low-cost compute available on demand?
    Even without parallelizing code, just launching a few big machines for a few
    hours to brute-force a calculations is a relatively new approach whereby you
    can throw lots of compute resources for a short time period and not have to
    pay for them after you’re done. That doesn’t even consider the potential
    efficiencies from breaking code down into serverless functions – this is a
    very interesting route for optimization.
