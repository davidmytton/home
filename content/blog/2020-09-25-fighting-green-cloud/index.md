---
title: "Fighting over who has the greenest public cloud"
date: 2020-09-25
modified: 2020-09-25
draft: false
tags: ["Cloud", "Data Center Energy", "Transparency"]
summary: "Public cloud price wars have ended, and a new battle over who is the 
greenest has begun."
url: fighting-over-who-has-the-greenest-public-cloud
---

Earlier in the decade, public cloud was a pricing battleground. AWS, Google and
Azure [announced regular price
decreases](https://techcrunch.com/2014/10/02/nobody-can-win-the-cloud-pricing-wars/). [Prices
for compute and
storage](https://www.zdnet.com/article/microsoft-aws-and-google-may-have-just-started-the-next-cloud-computing-price-war/) were
the usual targets, but innovative pricing mechanisms such as [Google’s sustained
use
discounts](https://cloudplatform.googleblog.com/2014/04/introducing-sustained-use-discounts.html) were
another attempt to compete.

Instead of focusing on pricing-led growth through price cuts, recent years has
seen the product portfolio take priority. The AWS revenue run-rate is $43B,
growing 29%; Azure $25B, growing 50%; and Google $8bn, growing 70%
([source](https://twitter.com/chetanp/status/1306990655944626176)). And [we know
that AWS is very
profitable](https://www.ben-evans.com/benedictevans/2020/9/6/amazons-profits).
Anyone who has played with all three platforms knows that this revenue
difference is reflected in the breadth and depth of the product portfolio.

Developers have no problem selecting the best tool for the job, and will happily
stitch together multiple products if necessary. The core development stack has
always focused on the programming language, database, and web server, with other
dependencies coming in as necessary (or built from scratch) – queues,
notifications, user authentication, monitoring. Now, it is increasingly likely
that a developer can get all those from a single vendor.

AWS was first to market, but Azure can match them on the number of products,
innovative features, and development velocity. You can’t quite buy everything
you need from AWS or Azure, but almost. Google comes a distant third.

Yet [the capex investment we see from the big
three](https://www.platformonomics.com/2020/07/follow-the-capex-clown-watch/) also
allows them to innovate on data centre design. What might look like marginal
gains in efficiency improvements [translate to major savings at the scale they
operate](https://davidmytton.blog/data-center-energy-and-the-importance-of-efficiency/).
This has a positive impact on their environmental footprint. This is the new
battleground.

In 2020, we have seen several major announcements from all three hyperscalers:

- Jan 2020: [Microsoft
  announced](https://blogs.microsoft.com/blog/2020/01/16/microsoft-will-be-carbon-negative-by-2030/) it
  will be carbon negative by 2030.
- Apr 2020: [Google
  announced](https://blog.google/inside-google/infrastructure/data-centers-work-harder-sun-shines-wind-blows/) its
  machine learning driven approach to moving workloads based on renewables
  availability.
- Jun 2020: [Amazon
  announced](https://blog.aboutamazon.com/sustainability/we-are-all-in-on-the-climate-pledge-net-zero-carbon-by-2040) it
  is aiming to be net-zero by 2040 rather than 2050.
- Jul 2020: [Microsoft
  announced](https://blogs.microsoft.com/on-the-issues/2020/07/21/carbon-negative-transform-to-net-zero/) a
  publicly available cloud emissions calculator.
- Aug 2020: [Microsoft
  announced](https://blogs.microsoft.com/on-the-issues/2020/08/04/zero-waste-carbon-emissions-2030/) zero
  waste by 2030.
- Sep 2020: [Google
  announced](https://blog.google/outreach-initiatives/sustainability/our-third-decade-climate-action-realizing-carbon-free-future) it
  had removed all its historic carbon emissions.
- Sep 2020: [Google
  announced](https://www.blog.google/outreach-initiatives/sustainability/supporting-greener-future-europe/) it
  aims to run 24/7 on renewable electricity ([I wrote about how challenging
  this
  is](https://davidmytton.blog/how-can-data-centers-use-100-renewable-electricity/) back
  in Feb)
- Sep 2020: [Microsoft
  announced](https://blogs.microsoft.com/blog/2020/09/21/microsoft-will-replenish-more-water-than-it-consumes-by-2030/) it
  will replenish more water than it consumes by 2030.

Google has been net zero the longest, since 2007. Microsoft achieved it in 2012.
Microsoft announced it would pay back all its historical emissions by 2050, but
Google achieved it in 2020. [Google has been working towards zero waste for
several
years](https://www.blog.google/outreach-initiatives/environment/six-google-data-centers-diverting-100/) and
Microsoft announced its 2030 goal this year. Microsoft is working towards [data
centre water
footprint](https://davidmytton.blog/how-much-water-do-data-centers-use/), but
Google is much more secretive there. Transparency is still a major problem
([Mytton,
2020](https://journalofcloudcomputing.springeropen.com/articles/10.1186/s13677-020-00185-8)),
but both companies are [taking
responsibility](https://davidmytton.blog/shifting-the-sustainability-focus-from-the-individual-to-the-corporation/) rather
than pushing it down on the consumer.

Where is Amazon in all this? AWS has several net-zero emissions regions and used
50% renewables across its operations in 2018, but this is nowhere near the level
of ambition we can see from Google and Microsoft. This is a problem because AWS
is the largest cloud provider. Customers can’t even calculate their own
emissions and offset them because the data isn’t published ([Mytton,
2020](https://journalofcloudcomputing.springeropen.com/articles/10.1186/s13677-020-00185-8)).

It is not fair to compare Amazon as a whole, because of their massive logistics
operation vs Google that just runs data centres, or Microsoft which has data
centres plus device manufacturing (mainly Xbox). Even so, AWS remains vague in
its commitments (no date for 100% renewables, for example). [Google publishes
quarterly PUE
values](https://www.google.com/about/datacenters/efficiency/) which show how
efficiently it uses energy in its owned data centres. AWS used to have its 2015
PUE in a website footnote, but was recently removed.

If AWS is not moving fast enough, the responsibility shifts back to its
customers. As one of the most high profile users of AWS, [Netflix has started
reporting](https://www.nasdaq.com/articles/netflix-just-started-reporting-renewable-energy-use-and-content-removal-2020-02-09) its
own “indirect energy use” i.e. AWS – [357,000MWh in
2019](https://s22.q4cdn.com/959853165/files/doc_downloads/2020/02/0220_Netflix_EnvironmentalSocialGovernanceReport_FINAL.pdf).
They have an unusual level of influence as a customer and can demand this type
of access, but unless other customers start adding pressure as the leader AWS
will feel no pressure to do better.

Either way, this new battleground is great to see. No company needs to be the
greenest today, but Microsoft and Google see the direction things are going.
Environmental impact, and climate change in particular, are becoming more
important issues for businesses responding to demand from their customers.
Governments will make demands and [corporates will use
procurement](https://davidmytton.blog/corporate-purchasing-an-unexpected-way-to-fight-climate-change/) to
ask for environmental checklists in the same way they do for security and
compliance because of the greater reporting requirements. This is a new cloud
war, and so far Amazon isn’t playing.
