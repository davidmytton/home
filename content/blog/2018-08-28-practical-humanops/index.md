---
title: "A practical guide to HumanOps - what it is and how to get started"
date: 2018-08-28
modified: 2018-08-28
draft: false
tags: ["HumanOps"]
canonicalUrl: https://blog.stackpath.com/what-is-humanops
url: a-practical-guide-to-humanops-what-it-is-and-how-to-get-started
---

_Originally written for the [StackPath
blog](https://blog.stackpath.com/what-is-humanops)._

Humans are a critical part of operating systems at scale, yet we rarely pay much
attention to them. Most of the time, energy and investment goes into picking the
right technologies, the right hardware, the right APIs. But what about the
people actually building and scaling those systems?

In 2016, Server Density launched [HumanOps](https://www.humanops.com/).
It [started with an event in
London](https://www.youtube.com/watch?v=d0a27yVWjCY&list=PLtl5khDVmtSiuGQcRxMVWgHvLzRfKjVK_) to
hear from some of the big names in tech about how they think about the teams
running infrastructure.

How can you reach your high availability goals without a team that is able to
build reliable systems, and respond when things go wrong? How does sleep and
fatigue affect system uptime? System errors are tracked, but what about human
error? Can it be measured, and mitigated?

[With the acquisition of Server Density by
StackPath](https://blog.stackpath.com/server-density-joins-stackpath), I am
pleased that HumanOps now has a team dedicated to continuing to build the
community. We’re open to anyone taking on responsibility for a local meetup but
will also be running our own series of events in major cities around the
world. [The first of these kicked off this week in San
Francisco.](https://www.heavybit.com/events/humanops-focusing-on-the-human-side-of-running-infrastructure/)

## What is HumanOps?

### The problem

A superhero culture exists within technical systems operations.

Being woken up to fix problems, losing sleep to make an amazing fix live in
production and then powering through a full day of work is considered to be
heroic effort.

There is little consideration for the impact this approach has on health, family
and long term well-being.

### The aim

Running complex systems is difficult and there will sometimes be incidents that
require heroic effort. But these should be rare, and there should be processes
in place to minimise their occurrence, mitigating the effects when they do
happen.

HumanOps events are about encouraging the discussion of ideas and best practices
around how to look after the team who look after your systems.

It considers that the human aspects of designing high availability systems are
just as important as the selection of technologies and architecture choices.

It’s about showing that mature businesses can’t afford to sacrifice their teams
and how the best managed organisations achieve this.

If [Etsy](https://www.computerweekly.com/news/450403359/HumanOps-Etsy-web-ops-boss-explains-how-inflated-workplace-expectations-contribute-to-staff-burnout), [Facebook](https://www.meetup.com/HumanOps-London/events/235104476/), [Spotify](https://www.youtube.com/watch?v=qVOq3QTukrE&list=PLtl5khDVmtSiuGQcRxMVWgHvLzRfKjVK_&index=3) and
the [UK
Government](https://www.youtube.com/watch?v=XpGvssf3t50&list=PLtl5khDVmtSiuGQcRxMVWgHvLzRfKjVK_&index=4) can
do this. So can you.

## How to implement HumanOps

The first step to implementing HumanOps is to understand and accept the key
principles.

### Key principles

1. Humans build & operate systems that have critical business impact.
2. Humans require downtime. They get tired, get stressed and need breaks.
3. As a result, human wellbeing directly impacts system operations.
4. As a result, human wellbeing has a direct impact on critical business
   systems.

HumanOps systems and processes follow from these principles.

### HumanOps systems & processes

There are many areas of operations where HumanOps can be applied, but there are
a few core areas which are worth starting with first. Each one of these could be
a separate blog post so here are a series of questions to start thinking about
your own process design.

- **On call**  
   This is where the most impact occurs. Being woken up to deal with a critical
  incident has a high impact, so it is important to design the on-call
  processes properly. Some key questions to ask: how is the workload shared
  across team members? How often is someone on-call and how long do they get
  off-call? What are the response time expectations for people at different
  escalation levels (e.g. do you have to stay at home by your computer or can
  you go out but with a longer response time?). Do you get time off after
  responding to an incident overnight? If so, is there any pressure to forgo
  that e.g. it should be automatic rather than requiring an active request. Do
  managers follow the same rules and set an example? Do you expect engineers
  to support their own code? Do you consider additional compensation for each
  on-call incident or is it baked into their standard employment contract? Do
  you prioritise bugs that wake people up?
- **Metrics  
   **You can’t improve something without measuring it. Critical out of hours
  incidents will happen, but they should be rare. Do you know your baseline
  alert level and whether that is improving? Do you have metrics about the
  number of alerts in general, number of alerts out of hours? Do you know if
  one person is dealing with a disproportionate number of alerts? Do you know
  which parts of the system are generating the most alerts? How long does it
  take for you to respond and then resolve incidents? How does this link to
  the business impact – revenue, user engagement, NPS? Are these metrics
  surfaced to the management team?
- **Documentation**  
   Only the smallest systems can be understood by a single person. This means
  writing and keeping documentation up to date needs to be a standard part of
  the development process. Runbooks should be linked to alerts to provide
  guidance on what alerts mean and how to debug
  them. [Checklists](https://en.wikipedia.org/wiki/The_Checklist_Manifesto) must
  form a part of all human performed tasks to mitigate the risk of human
  error. How do you know when documentation is out of date? Who takes
  responsibility for updating it? How often do you test?
- **Alerts**  
   Most system operators know the pain of receiving too many alerts which are
  irrelevant and don’t contain enough information to resolve the problem. This
  is where linked documentation comes in but the goal should be that alerts
  don’t reach humans except as a last resort. Interrupting a human should only
  happen if only a human can resolve the problem. This means automating as
  much as possible and triggering alerts based on user-impacting system
  conditions, not just on component failures where the system can continue to
  operate. Are your alerts actionable? Do they contain enough information for
  the recipient to know what to do next? Are they specific enough to point to
  the failure without resulting in a flood if there is a major outage?
- **Simulation  
   **A large part of the stress of incidents is the uncertainty of the
  situation coupled with the knowledge that it is business / revenue
  impacting. Truly novel outages do happen but much of the incident response
  process can be trained. Knowing what you and each of your team members need
  to do and when will streamline response processes. Emergency response teams
  do this regularly because they know that major incidents are complex and
  difficult to coordinate ad-hoc. Everyone needs to know their role and what
  to do in advance. War gaming scenarios to test all your systems, people and
  documentation helps to reveal weaknesses that can be solved when it doesn’t
  matter as much, and teach the team that they can [apply haste without
  speed](https://en.wiktionary.org/wiki/more_haste,_less_speed). How is the
  incident initially triaged? What are the escalation processes? How does
  stakeholder communication work? What happens if your tools are down too e.g.
  is your Slack war room hosted in the same AWS region as your core
  infrastructure?

The idea behind HumanOps principles is to provide a framework for focusing on
the human side of infrastructure.

What’s the point of spending all that time and money on fancy equipment if the
people who actually operate it aren’t being looked after? Human wellbeing is not
just a fluffy buzzword – it makes business sense too.

The idea behind HumanOps events are to share what works and what doesn’t, and
demonstrate that the best companies consider their human teams to be just as
important as their high tech infrastructure.

Over the coming months I’ll be writing more about each of these topics and
sharing the videos of other organisations explaining how they do it, too.

If you’re interested in attending, speaking or even running a HumanOps event
near you, [check out the website event listings](https://www.humanops.com/) and
get in touch if there’s nothing nearby.
