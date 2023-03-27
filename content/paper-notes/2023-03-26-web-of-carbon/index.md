---
title: "Paper Notes - The world wide web of carbon"
date: 2023-03-26
modified: 2023-03-26
draft: false
tags: ["Paper Notes", "Cloud", "IT Energy", "Data Center Energy", "Network Energy"]
summary: "Will we ever be able to accurately assess the carbon footprint of IT? 
Could a relational footprint methodology be more useful? Paper notes on Pasek 
et al (2023)."
canonicalUrl: https://www.devsustainability.com/p/paper-notes-the-world-wide-web-of-carbon
url: paper-notes-the-world-wide-web-of-carbon
---

## Paper

Pasek, A., Vaughan, H., & Starosielski, N. (2023). The world wide web of carbon:
Toward a relational footprinting of information and communications technology’s
climate impacts. Big Data & Society, 10(1).
<https://doi.org/10.1177/20539517231158994>

## General Notes

- There are several problems with assessing the environmental impact of IT which
  mean that it may never be possible to create an accurate account.
- The paper accurately describes the differences in the key publications:

> There are ongoing difficulties in acquiring, analyzing, and sharing
> high-quality data about the sector and remarkably enduring dissensus about
> research methods and implications. According to different voices in this
> debate, the carbon and energy costs of the Internet are growing (Andrae, 2020;
> Belkhir and Elmeligi, 2018; Ferreboeuf, 2019; Makonin et al., 2022), shrinking
> (Accenture Strategy, 2015; Aslan et al., 2018; Lange et al., 2020), holding
> flat (Masanet et al., 2020; Shehabi et al., 2018), or even moving in all
> directions at once, depending on how you count (Bieser and Hilty, 2018;
> Coroama et al., 2014; Court and Sorrell, 2020; Lorincz et al., 2019; Malmodin
> et al., 2014; Sorrell et al., 2020). Even within peer-reviewed literature
> estimates regarding the carbon intensity of network transmission vary by up to
> five orders of magnitude (Aslan et al., 2018). These differences matter; they
> make consensus on empirical questions impossible and polarize wider public
> debates.

- It also accurately diagnoses the high-level factors which cause these
  differences: data access, assessment methodologies, use of averages,
  functional units, system boundaries, and focusing on energy efficiency ([most
  of which have been highlighted
  before](https://doi.org/10.1016/j.joule.2021.05.007)). However, it doesn’t
  consider the technical differences between the methodologies underlying these
  conclusions (or the differences in the key publications listed in the quote
  above).
- For instance, the key difference between the “growing” and “holding flat”
  perspectives is the link between energy consumption and data volume. The
  Andrae (et al) modeling assumes that energy consumption and data volume are
  directly proportional. A rapid increase in data volume (as has been happening,
  and will continue) would result in an equally rapid increase in energy
  consumption. [This isn’t
  true](https://www.devsustainability.com/p/approaches-to-calculating-network-website-energy-and-carbon).
  There is no direct relationship between data volume and energy consumption.
  This paper makes it seem like there are real debates in the literature, when
  actually it is more about whether the models present an accurate picture of
  reality.
- Access to consistent industry data is a problem, but the paper focuses only on
  the researcher affiliations rather than discussing the details of data
  sourcing. This was one of the major issues identified in [the data center
  energy estimates paper I co-authored last
  year](https://doi.org/10.1016/j.joule.2022.07.011). Transparency is improving.
  Only last year, [Lundén et al released an updated
  paper](https://doi.org/10.3390/su14052637) based on survey data from 15
  different telecom operators covering 21 European countries to provide an
  updated analysis of energy consumption and carbon footprint for 2015-2018.
  This follows from [their earlier analysis of
  2010-2015](https://www.diva-portal.org/smash/get/diva2:1177210/FULLTEXT01.pdf).
  This also uses more granular, country-specific carbon intensity factors (which
  is a legitimate criticism of certain methodologies that only use global
  averages). [Another paper looks at real world observations for cellular
  networks in Belgium](https://link.springer.com/10.1007/s12243-022-00932-9).
  These are recent papers with real data, a big improvement towards more
  transparency.
- System boundaries are also a major factor in differing assessments, but that
  is inherent in lifecycle assessments. Insufficient care is taken with
  comparisons because the reader did not understand the system boundary and/or
  the publication does a poor job at describing the boundary it is using. This
  was another issue I found [analyzing center energy
  estimates](https://doi.org/10.1016/j.joule.2022.07.011) - comparison between
  papers with incompatible (or inconsistent) system boundaries is common.
- Pasek et al correctly analyzes the differences between top-down and bottom-up
  assessment methodologies, but misses when they are appropriate to use. They
  say “top-down studies have the appeal of being better adapted to estimate
  future trajectories and outcomes.” In reality, top-down methodologies should
  only be used for retrospective analysis i.e. when you have the data and want
  to calculate intensities or allocate carbon footprint. Bottom-up estimates are
  a better basis to project a few years into the future, but all must make
  assumptions e.g. future shipment figures, or changes in technology, which
  become less accurate the further into the future they project.

![A table showing the three main approaches to assessing data center
energy](dc-analysis-approaches.png "Characteristics of the three main approaches
to assessing data center energy—bottom-up, top-down, extrapolation. From:
[Mytton & Ashtine (2022)](https://doi.org/10.1016/j.joule.2022.07.011).")

- With the assumption that these factors may never be resolved the paper
  proposes that relational footprinting may be the solution as “an empirical and
  strategic orientation toward demarcating particular relationships between
  elements—geographic, spatial, technical, and social—within a broad
  infrastructural network”. In particular, they say:

> …if the carbon intensity of data derives predominantly from its location,
> rather than its distance, then the ‘where’ of ICT becomes a modulating factor
> to its size. From this perspective, networks might be re-configured to
> leverage more intense development in renewably-powered locations and degrowth
> in fossil-fuel-based locations (say, to connect more data centers in Brazil
> and less in Qatar). Emissions can thus be lowered, with certainty, and without
> first winning global support for a dramatic endorsement or curtailment of
> industry business models or the value of particular forms of digital content.

- Despite the claim that relocating (or restricting the location of) networks
  and data centers doesn’t require changes in business models, it doesn’t really
  explore the details of what this would mean in practice. There are always
  multiple factors when considering infrastructure locations. Land cost,
  availability of (clean) energy, grid infrastructure requirements (new buildout
  or connection to existing substations), location of fibre networks (new, or
  existing), proximity to users, availability of water, availability of staff,
  ease of access, data residency requirements, local regulations and permitting
  all play a role. The paper mentions a few of these (e.g. latency and data
  residency/privacy), but only in passing. The primary driver of this proposal
  seems to be social/political.
- Finally, it doesn’t provide any methodology, examples, calculations, or
  suggestions for how to implement “relational footprinting”.

## Conclusions

The main limitation of this proposal is that it is qualitative rather than
quantitative. This paper provides no methodology for assessing the environmental
impact in any measurable or comparable way. The focus on sub-sea cables is
unusual because their impact is described primarily as a social case study of -
their actual environmental impact is insignificant. The social impacts are
important, but it’s unclear how they are relevant to “climate impacts”.

I find this paper quite strange. It purports to provide a solution to the
challenges in assessing the environmental impact of IT, accurately diagnoses the
high-level problems, but then completely misses the technical details. Perhaps
this is because I’m used to reading scientific papers rather than social
“science”[^social], so maybe that isn't the goal. Indeed, it suggests that
numbers are suspect:

[^social]:
    I also found the wording and phrasing of the whole article to be
    overly verbose and imprecise.

> Throughout this study, we are reminded of Ted Porter’s famous observation that
> the credibility of numbers is a profoundly social problem, created and
> sustained by groups that often lack the public legitimacy and internal unity
> necessary to democratically resolve conflicts within and between
> institutions…Scholars overlook these complexities when they uncritically draw
> on the charismatic numbers of a single study.

The conclusion of the paper is that accurate assessments may be impossible so a
different approach is needed, but that approach is not described in any way that
is reproducible.

My conclusion is that past assessments have methodological flaws which can be
addressed and better data made available. We need to improve our understanding
of the models and communicate better so that they can be used outside of the
technical literature. This is already happening and is an important part of how
the field progresses, but there is more to do.
