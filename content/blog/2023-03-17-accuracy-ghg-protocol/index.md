---
title: "Improving the accuracy of the GHG protocol in time and space"
date: 2023-03-17
modified: 2023-03-17
draft: false
tags: ["Data Center Energy", "Energy Systems", "Cloud", "Transparency"]
summary: "The GHG Protocol needs to evolve to better represent the complexity of how energy markets work."
canonicalUrl: https://www.devsustainability.com/p/improving-the-accuracy-of-the-ghg
url: improving-the-accuracy-of-the-ghg-protocol
---

[A
survey](https://ghgprotocol.org/survey-need-ghg-protocol-corporate-standards-and-guidance-updates)
on the need for updating the Greenhouse Gas (GHG) Protocol standards recently
closed. Having been in existence since 2004 (with scope 2 and scope 3 guidance
published in 2015 and 2013), it is a good time to consider changes.

Over the last few years, there has been a surge in interest in reporting
accurate GHG figures. Many companies now report annually, either voluntarily or
because they are large enough to be required by laws. The GHG protocol is the
standard for these reports, even if they often are published in annoying formats
(glossy PDFs).

In IT, transparency has also been improving. A year ago, [AWS released its
carbon calculator](/cloud-emissions-transparency-stage-1-completed-what-next/)
to bring it up to a similar level as Google and Microsoft. There have been [some
recent comments about AWS defunding their sustainability
initiatives](https://www.linkedin.com/posts/adriancockcroft_amazon-denies-claims-hiring-freeze-is-slowing-activity-7035729287030730752-eIog),
but you can now at least get emissions numbers based on your cloud carbon
footprint.

Unfortunately, the calculations are not all equal. Google is the most
transparent with its methodology. AWS is the least - they give you a number, but
the documentation is limited. This makes it impossible to compare between
providers, but even within a single provider there insufficient detail to
properly link energy generation with usage.

![An 18th century painting of an electricity grid with gases coming out of the
trees](dalle-painting.png "Generated by DALL-E 2 (“an 18th century painting of
an electricity grid with gases coming out of the trees”)")

Can this be addressed with updates to the GHG protocol? [Google published their
submission](https://www.gstatic.com/gumdrop/sustainability/google-2023-GHGP-Survey-Submission.pdf)
to the GHG Protocol survey, and it’s a point they highlighted as a priority for
change:

> Under current GHGP methodologies, the actions that are credited as emissions
> reductions within companies’ inventories do not align sufficiently with the
> real-world GHG impact of those actions. Company strategies and actions that
> differ widely in effectiveness, both in their impact on a company’s own GHG
> footprint and on broader energy and economic systems, are in many cases
> credited equally…The updated GHGP should remedy this by more closely aligning
> credit for GHG reductions with real and measurable impacts of company actions.

Reporting also still requires lengthy analysis, often involving expensive
consulting projects. It is very difficult to get data, particularly if you are a
small business. The near real-time reporting we’re used to in finance is not yet
possible in carbon accounting, although the cloud providers do a good job of
updating their calculations frequently. Google is the best at this (every
month), AWS the worst (3 months lag). This is going to be important for proper
scope 3 reporting so that direct (scope 1 and scope 2) emissions figures can be
reported through the supply chain.

Improving the granularity of electricity emissions data will help here, not
least for serving as an input for [temporal and spatial load
shifting](/influencing-carbon-emissions-of-ai/). This is important to be able to
link clean energy generation to demand, says Google:

> Under today’s GHGP guidance, geographic boundaries for scope 2 do not
> correspond to the physical markets where a company consumes electricity. A
> company can purchase Energy Attribute Certificates (EACs) far from where it
> consumes electricity, because the electricity represented by EACs is not
> required to be deliverable to the grid(s) where the company operates. Thus,
> EACs that are physically disconnected from underlying electricity consumption
> function effectively as offsets: they are reductions claimed elsewhere to
> compensate for a company’s electricity based emissions. This approach has
> become widespread in practice under today’s scope 2 guidance, despite the
> scope 2 standard ostensibly prohibiting the use of offsets to reduce a
> company’s emissions.

This is a limitation with how instruments like RECs are accounted for. There’s a
disconnect between the grid mix at the time of use and using products like RECs
to mitigate emissions. It’s why unbundled RECs are so cheap and are [ineffective
at achieving
anything](/recs-cannot-be-used-to-back-claims-of-100-renewable-energy/):

> The Residual Mix of electricity from the grid is defined as the leftover once
> the consumed GOs are taken out from the total production mix. The basic idea
> is that companies (and consumers) that do not purchase the GOs or RECs, get
> this Residual Mix from the grid. However, the calculation of the Residual Mix
> in a country is still highly inaccurate. The reason for this inaccuracy is
> that there is a time delay between the trading of electricity and the trading
> of the corresponding RECs and GOs. The RECs and GOs are created in the month
> after the month of the production, or later, and the trading has a maximum
> delay of 1 year for GOs, and 21 month for RECs. It is mathematically not
> correct to subtract data from those two different trading systems, because
> Solar and Wind power have heavy fluctuating production characteristics, and
> the unbundled hydropower GOs are issued irregularly. Concluding: the Residual
> Mix should not be used in LCA.[^eco]

[^eco]:
    [Guarantees of Origin, Renewable Energy Certificates and the Residual
    Mix in LCA](https://www.ecocostsvalue.com/lca/gos-and-recs-in-lca/)

Such distortions show up in things like Norway’s emissions factors which are 10
kg CO2/MWh on a grid-level, but 402 kg CO2/MWh on a residual basis because most
of the clean energy credits produced in Norway are actually sold and claimed
outside of the region[^google]. If these are then used to produce claims of 100%
renewable energy on an annual basis, the emissions reductions can be overstated
by as much as 50%[^notenough]. If you see anyone making such claims, the only
safe assumption is that they are bogus.

[^google]:
    pg13 of [Google’s survey
    response](https://www.gstatic.com/gumdrop/sustainability/google-2023-GHGP-Survey-Submission.pdf).

[^notenough]:
    [Why 100% Renewable Energy Is Not
    Enough](https://doi.org/10.1016/j.joule.2019.05.002)

One of my first peer-reviewed articles was on this topic back in 2020 [where I
analyzed the suitability of the GHG Protocol for calculating cloud carbon
emissions](https://doi.org/10.1186/s13677-020-00185-8). The cloud providers
subsequently made this a lot easier through their cloud carbon calculator
products. That was the first step - getting a number.

Now the GHG Protocol needs to evolve to better represent the complexity of how
energy markets work, how companies respond to incentives to get to net zero, and
how that flows through supply chains to ensure all organizations can produce
accurate emissions inventories.
