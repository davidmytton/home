---
title: "Paper notes – Energy efficiency across programming languages"
date: 2022-07-20
modified: 2022-10-08
draft: false
tags: ["Paper Notes", "IT Energy", "Programming", "Energy Efficiency"]
summary: "Which languages are the fastest and most energy efficient? The simple 
answer is: C, C++, Rust. The accurate answer is: it depends."
canonicalUrl: https://www.devsustainability.com/p/paper-notes-energy-efficiency-across-programming-languages
url: paper-notes-energy-efficiency-across-programming-languages
---

## Papers

1. Pereira, R., Couto, M., Ribeiro, F., Rua, R., Cunha, J., Fernandes, J.P., and
   Saraiva, J. (2017). Energy efficiency across programming languages: how do
   energy, time, and memory relate? In Proceedings of the 10th ACM SIGPLAN
   International Conference on Software Language Engineering (ACM), pp.
   256–267. <https://doi.org/10.1145/3136014.3136031>
2. Pereira, R., Couto, M., Ribeiro, F., Rua, R., Cunha, J., Fernandes, J.P., and
   Saraiva, J. (2021). Ranking programming languages by energy efficiency.
   Science of Computer Programming *205*,
   102609. <http://dx.doi.org/10.1016/j.scico.2021.102609>

## Notes

- 5 years is a long time in technology, so it’s a good thing the same authors
  have a followup paper published in 2021 to take another look. The 2021 paper
  validates the 2017 results.

- There is a general assumption that energy consumption is related to execution
  time because `Energy = Power * Time`. However, this paper shows that both Power
  and Time can vary across language.

- Benchmarks are always a risky business – they can be easily set up to show
  what you want them to show. This paper uses the [The Computer Language
  Benchmarks
  Game](https://benchmarksgame-team.pages.debian.net/benchmarksgame/index.html) (CLBG)
  as a well understood suite of language benchmarks to attempt to provide
  reproducible test scenarios.

  - The 2021 paper adds a more “real world” analysis on a codebase that better
    represents day-to-day programming problems. This does not show any major
    differences that the CLBG misses and validates the results from 2017.

- The tests were performed using Intel’s RAPL tool, which provides energy
  consumption metrics from Intel CPUs. This was a good choice at the time, but
  in 2022 ARM chips are of major relevance. Not only are they in billions of
  mobile devices – where energy efficiency is really important – but Apple is
  pushing their entire line of computers to ARM. Energy efficiency is just as
  important in laptops.

- Tests were done on an Ubuntu desktop. This might make the test setup easier,
  but how relevant is it as representative of real world environments? Using
  server hardware would be interesting, particularly as ARM is also growing on
  the server – [Google Cloud just announced ARM-based
  instances](https://cloud.google.com/blog/products/compute/tau-t2a-is-first-compute-engine-vm-on-an-arm-chip) so
  we now have all three cloud providers offering ARM in the data center.

- OS-level optimization would be another factor to consider. Mobile devices have
  done this for a while, but [Apple talks about the different types of cores in
  its systems](https://developer.apple.com/news/?id=vk3m204o). High-efficiency
  vs high performance cores will express different characteristics:

> An app may execute threads on both P and E cores over a period of time. The OS
> places threads on P or E cores based on the following criteria: Information
> your app provides, Observation of the app’s workload, Observation of the
> system as whole. On Apple Silicon Macs, the system observes applications and
> daemons separately from each other. This allows the system to execute them
> with individual efficiency and performance characteristics. As an example, an
> app running in the background may have its threads placed on E cores to
> optimize battery life while the foreground app is taking advantage of P cores.
>
> <cite>[Optimize for Apple Silicon with performance and efficiency
> cores](https://developer.apple.com/news/?id=vk3m204o), Apple.</cite>

- The results show that C is the fastest and most energy efficient programming
  language. The top 5 languages were all fairly consistent across all three
  considerations – energy efficiency vs execution time vs memory usage.

- Compiled languages are almost always fastest and most energy efficient

- The most energy efficient language is almost always the fastest language, but
  there is no one language that consistently beats all other languages in every
  benchmark.

- The methodology ran each benchmark 10 times and removed outliers, then
  calculated median, mean, standard deviation, min, and max values. The authors
  state this allowed them to remove variability caused by system processes. It
  would be interesting to run these tests in serverless environments because
  cold-starts are an important characteristic that needs to be handled and may
  have an impact on the overall results in cloud environments.

![Table of programming language energy efficiency](normalized-energy-time-memory-results.png "The global results (on average) for Energy, Time, and Mb normalized to the most efficient language in that category. **Source:** [Pereira, et al. (2021)](http://dx.doi.org/10.1016/j.scico.2021.102609)")

## Conclusions

Which languages are the fastest and most efficient?

The simple answer is: C, C++, Rust.

The accurate answer is: it depends.

To quote from the 2017 paper:

> The most common performance characteristics of software languages used to
> evaluate and choose them are execution time and memory usage. If we consider
> these two characteristics in our evaluation, C, Pascal, and Go are equivalent.
> However, if we consider energy and time, C is the best solution since it is
> dominant in both single objectives. If we prefer energy and memory, C and
> Pascal constitute the Pareto optimal set. Finally, analyzing all three
> characteristics, this scenario is very similar as for time and memory.
>
> ...
>
> If the developer is only concerned with execution time and energy consumption,
> then yes, it is almost always possible to choose the best language.
> Unfortunately, if memory is also a concern, it is no longer possible to
> automatically decide for a single language.

Which means you have to make a decision based on what you are trying to
optimize: time & memory, energy & time, energy & memory, or even energy & time &
memory!

![Comparison of languages by objective](objective-sets.png "Pareto optimal sets for different combination of objectives. **Source:** [Pereira, et al. (2021)](http://dx.doi.org/10.1016/j.scico.2021.102609)")
