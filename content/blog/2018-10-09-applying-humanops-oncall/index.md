---
title: "Applying HumanOps to on-call"
date: 2018-10-09
modified: 2018-10-09
draft: false
tags: ["HumanOps"]
canonicalUrl: https://blog.stackpath.com/applying-humanops-to-on-call
url: applying-humanops-to-on-call
---

_Originally written for the [StackPath
blog](https://blog.stackpath.com/applying-humanops-to-on-call)._

One of the two core foundations of SaaS monitoring is alerting (the other being
metric visualization and graphing). Alerting is designed to notify you when
things go wrong in your data center, that there’s a problem with your website
performance, or if you’re experiencing server downtime. More specifically,
infrastructure monitoring and website monitoring are designed to notify you in
such a way that you can respond and try to fix it. That often means waking
people up, interrupting dinners, and taking people away from their family to
deal with a problem.

When the very nature of a product deliberately has a negative impact of the
quality of life of your customers, it is your responsibility as the vendor to
consider how to mitigate that impact. Trying to understand how [StackPath
Monitoring](https://www.stackpath.com/services/monitoring/) impacts our
customers through their on-call processes was why we
started [HumanOps](https://www.humanops.com/).

## So how do you apply HumanOps principles to (re)designing your approach to on-call?

HumanOps is made up of 4 key principles. These are explained in more detail in
the [What is HumanOps](https://blog.stackpath.com/what-is-humanops) post, but
essentially it boils down to:

1. Humans build & operate systems that have a critical business impact.
2. Humans require downtime. They get tired, get stressed, and need breaks.
3. As a result, human wellbeing directly impacts system operations.
4. As a result, human wellbeing has a direct impact on critical business
   systems.

These can be applied through considering some key questions about how on-call
processes work.

## How is on-call workload shared across team members?

It’s standard practice to have engineers be on-call for their own code. Doing so
provides multiple incentives to ensure the code is properly instrumented for
debugging, has appropriate documentation for colleagues to debug code they
didn’t write, and, of course, to rapidly fix alerts which are impacting your own
(or your colleagues) on-call experience. If you’re being woken up by your own
bad code, you want to get it fixed pretty quickly!

With the assumption that engineers support their own code, the next step is to
share that responsibility fairly. This becomes easier as the team grows but even
with just 2-3 people, you can have a reasonable cycle of on/off call. We found
that 1-week cycles Tuesday – Tuesday work well. This is a long enough period to
allow for a decent “off-call” time and has a whole working day buffer to discuss
problems that might have occurred over the weekend.

You also want a formal handoff process so that the outgoing on-call engineer can
summarize any known issues to the person taking over.

## How do you define primary and secondary escalation responsibilities?

The concept of primary/secondary is a good way to think about on-call responders
and the Service Level Agreement they commit to with each role.

The primary responder typically needs to be able to acknowledge an alert and
start the first response process within a couple of minutes. It means they have
to be by an internet connected computer at all times. This is not a 24/7 NOC,
which is a different level of incident response.

Contrast this with a secondary who may be required to respond within 15-30
minutes. They are there as a backup in case the primary is suddenly unreachable
or needs help, but not necessarily immediately available. This is an important
distinction in smaller teams because it allows the secondary to go out for
dinner or be on public transport/driving for a short period of time (i.e. they
can live a relatively normal life!). You can then swap these responsibilities
around as part of your weekly on-call cycle.

## What are the expectations for working following an incident?

An alert which distracts you for 10 minutes early evening is very different from
one which wakes you up at 3 a.m. and takes 2 hours to resolve, preventing you
from going back to bed again because it’s now light outside.

In the former situation, you can still be productive at work the next day, but
in the latter, you’re going to be very fatigued.

It’s unreasonable to expect on-call responders to be completely engaged the day
after an incident. They need to have time to recover and shouldn’t feel
pressured to turn up and be seen.

The best way I’ve seen to implement this is to have an automatic “day off”
policy which is granted without any further approval, and leave it to the
discretion of the employee to decide if they need a full day, work from home, or
just to sleep in for the morning.

Recovery is necessary for personal health but also to avoid introducing human
errors caused by fatigue. Do you really want someone who has been up all night
dealing with an incident committing code into the product or logging into
production systems?

This should be tracked as a separate category of “time off” in your calendar
system so that you can measure the impact of major on-call incidents on your
team.

It also applies if there is a daytime alert which takes up a significant amount
of time during a weekend or holiday. The next work-day should be taken as
vacation to make up for it.

Having the employee make the decision, but with it defaulting to “time off
allowed” avoids pressure to come in to work regardless. Reducing the cultural
peer pressure is more challenging, but managers should set the expectation that
it is understood that you will take that time off, and make sure that everyone
does.

## How do you measure whether your on-call process is improving?

Metrics are key to HumanOps. You need to know how many alerts are being
generated, what percentage happen out of hours, what your response times are,
and whether certain people are dealing with a disproportionate number of alerts.

These metrics are used for two purposes:

1. **To review your on-call processes.** Do you need to move schedules around
   for someone who might have had more of their fair share of alerts? Are
   people taking their recovery time off? Are people responding within the
   agreed SLAs? If not, why not?
2. **To review which issues should be escalated to engineering planning.** If
   alerts are being caused by product issues they need to be prioritized for
   rapid fixes. Your engineers should be on-call so they will know what is
   impacting them, but management needs to buy into the idea that any issues
   that wake people up should be top priority to fix.

Eliminating all alerts is impossible, but you can certainly reduce them. You can
then track performance over time. You’ll only know how you’re doing if you
measure everything though!

## How are you implementing HumanOps?

We’re interested in hearing how different companies run their on-call so we can
share the best ideas within the community. Let me know how you’re implementing
the HumanOps principles. Also, we encourage you to come along to one of our
HumanOps events to discuss with the community. [Email
me](mailto:david@davidmytton.co.uk) or mention me on
Twitter [@davidmytton](https://twitter.com/davidmytton).
