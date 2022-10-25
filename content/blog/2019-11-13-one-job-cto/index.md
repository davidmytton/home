---
title: "The one job of the early stage startup CTO"
date: 2019-11-13
modified: 2019-11-13
draft: false
tags: ["Startups"]
summary: "With so many things happening in early stage startups, what is the 
one thing the CTO should focus their time on?"
url: the-one-job-of-the-early-stage-startup-cto
---

Startup leadership roles are unusual because the job changes so rapidly. Someone
doing the role of CEO or CTO when the company is founded will find themselves
doing something very different 18 months later.

> When hiring executives, look for people who have the experience and background
> that would make them a good fit or hire for the next 12–18 months. Anything
> shorter than that and they will not be able to scale sufficiently far relative
> to the time it takes to hire them. Anything longer and you will over-hire and
> end up with someone who is a bad fit for the job.
>
> <cite>Gil, Elad. High Growth Handbook (p. 119)</cite>

The startup CTO is usually the founder with the best technology background and
they will usually be the one leading the development of the initial product.
However, the word “Technology” in the title is misleading because it is not the
most important part.

For early stage startups seeking product market fit, the CTO’s one job is to
figure out how to hit the business milestones using technology. Understanding
the business is what differentiates the CTO from a software engineer. This means
setting up the technology team and processes to iterate quickly based on
feedback from commercial interactions with early customers.

The early stage CTO must be comfortable with technical debt and inefficient
processes. They need to be able to make the tradeoff between building the
perfect technical architecture and creating something good enough. They must
understand what is built in the early months is unlikely to survive for long,
and most of the codebase will be rewritten at some point. However, they must
also [decide when it’s right to do that rewriting and
refactoring](https://davidmytton.blog/rewriting-refactoring-rearchitecting-when-is-the-right-time/),
which is never in the early stages of startup life and [never the whole codebase
in one
go](https://www.joelonsoftware.com/2000/04/06/things-you-should-never-do-part-i/).

The early stage startup CTO only focuses on the one or two elements that truly
differentiate the company, and outsources everything else to SaaS or cloud
products. This means using cloud services, not building your own. It means
creating a monolithic codebase rather than hundreds of microservices. It means
tying together 3rd party services and paying with cash rather than time. Later,
it means deciding which services to bring in-house and which to just keep paying
for. Netflix [runs their own
CDN](https://openconnect.netflix.com/en_gb/) because this is core to their
business, but everything else is run on AWS. The early stage startup CTO has to
figure this out for their own business.

Developer productivity is affected by bad code and reliability (redundancy,
tests, deploys) requires investment. The early stage startup CTO has to decide
what is critical to build now and what can wait. The priority is proving whether
the business is viable.

It’s an uncomfortable state to be in – chaos – but the early stage startup CTO
will know that it only lasts for a short time. Unless the product is in a
regulated industry or safety critical, these tradeoffs have to be made because
money and time are so limited. Think of the [reliability problems of early
Twitter](https://en.wikipedia.org/wiki/Twitter#Outages), or the [poor client
performance of
Slack](https://slack.engineering/reducing-slacks-memory-footprint-4480fec7e8eb).
These annoyed users but in the end didn’t negatively affect the outcome.

If the product is compelling enough, users will accept rough edges for a period
of time. “[How
long?](https://davidmytton.blog/rewriting-refactoring-rearchitecting-when-is-the-right-time/)”
is another difficult question the early stage startup CTO has to answer.

Only as the company scales (in terms of people and revenue) will the CTO start
to think about the Technology element of their title. This will include helping
teams make technical and architectural decisions as well as building the
management structures around how engineering is run. Eventually, a new role –
VP, Engineering – splits off to focus on the people:

> A VP Engineering is ideally a great manager and a great team builder. He or
> she will be an excellent recruiter, a great communicator, and a great issue
> resolver. The VP Eng’s job is to make everyone in the engineering organization
> successful and he or she needs to fix the issues that are getting in the way
> of success.
>
> A CTO is ideally the strongest technologist in the organization. He or she
> will be an architect, a thinker, a researcher, a tester and a tinkerer. The
> CTO is often the technical co-founder if there is one (and you know I think
> there must be one).
>
> <cite>[VP Engineering vs
> CTO](https://avc.com/2011/10/vp-engineering-vs-cto/)</cite>

Until then, the only thing the CTO should be focused on is [using technology to
enable the startup business
goals](http://www.startuplessonslearned.com/2008/09/what-does-startup-cto-actually-do.html).
Business, through technology. Everything else is secondary.
