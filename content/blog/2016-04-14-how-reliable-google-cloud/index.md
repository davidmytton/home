---
title: "How reliable is Google Cloud?"
date: 2016-04-14
modified: 2016-04-14
draft: false
tags: ["Cloud"]
url: how-reliable-is-google-cloud
---

Nothing is 100% reliable. When designing application architecture, you have to
assume there will be failures. Historically, this has meant deploying across
racks, rooms and data centres to ensure that local switch, power and geographic
incidents do not affect your entire infrastructure.

When deploying on the cloud, this translates to deploying across zones and
regions. A zone is supposed to be isolated from other zones but close enough to
allow low latency and low cost networking. However, since zones are close by,
they are still susceptible to geographic events e.g. Storms. That’s why
you [deploy across multiple
regions](http://techblog.netflix.com/2016/03/global-cloud-active-active-and-beyond.html).
For complete redundancy, [provider diversity is the ultimate
goal](http://highscalability.com/blog/2014/12/1/auth0-architecture-running-in-multiple-cloud-providers-and-r.html).

Zone and regional failures are bad but with proper design, you can handle them
transparently to your users. This is why it’s a big deal when a cloud provider
suffers a global outage, as Google did this week.

## The April 2016 Google Cloud outage

Google posted [a very detailed post
mortem](https://status.cloud.google.com/incident/compute/16007) of the 18 minute
global networking outage on April 11 in which all Compute Engine IPs were
withdrawn from routing. There were failures in multiple levels of “defence in
depth” where a cascade of software bugs resulted in bad configs being rolled
out.

The post mortem shows how, [as with modern aircraft, it is never a single
component
failure](https://blog.serverdensity.com/cloud-storage-failures-the-perfect-storm/) but
a combination of many complex factors. Our systems are now sufficiently complex
that simple failure cases are rare. Redundancy is built in.

Although you might point out that there was a failure with testing and ask why
nobody was monitoring the rollout stages after it was triggered, this post
mortem demonstrates the systems in place that make up a modern, well engineered
cloud provider.

Humans can’t be relied upon to monitor every change, especially if they’re
happening regularly, so the real improvement to follow this outage is with the
QA and test coverage for the automated systems.

It also highlights the excellent response time for their reliability engineers
and how training was an important factor in reducing the length of the outage.

## Historical Google Cloud outages

This is not the first time Google has had a global outage. Indeed, in the past
they happened disappointingly often.

- [August 2015:](https://status.cloud.google.com/incident/compute/15055) A
  global networking outage caused by rolling out a software bug. A failure in
  testing and an implied global rollout without canaries.
- [March
  2015:](https://groups.google.com/forum/#!topic/gce-operations/fynnXnb2OFs) A
  networking outage with variable impact across zones/regions causing packet
  loss. A failure in testing and a global rollout without canaries.
- [September
  2014:](https://groups.google.com/forum/#!topic/gce-operations/1uw-qEqjBdo) Rolling
  reboot of large numbers of GCE instances in all regions. Global rollout
  without canaries.

There have also been previous region level outages caused by similar
circumstances, for example in [October
2014](https://groups.google.com/forum/#!topic/gce-operations/NmBFtpM9lmo) the
Asia East region suffered a networking outage due to a bug in a networking
upgrade procedure. And again more recently in [February
2016](https://status.cloud.google.com/incident/compute/16002).

This is important because [Google
claims](https://cloud.google.com/compute/docs/zones):

> Because each zone is an independent entity, zone failures do not affect other
> zones.

## Is Google Cloud getting more reliable?

From the latest post mortem, we can see that Google has added multiple layers of
protection that were not present in previous outages. These include:

- **Automation**. Using tools to apply configuration changes makes it easy to
  do them consistently and repeatedly. You mitigate human errors such as typos
  or incorrect configurations.
- **Verification**. Google has software which not only generates the config
  but also verifies it. The problem is the most recent outage was that
  although the verification step discovered the problems, the rollout was not
  aborted due to bugs in the rollout process.
- **Staged rollouts**. The incident actually began several hours before the
  global impact was seen. Past outages have seen changes applied globally at
  the same time but now changes are rolled out gradually. Unfortunately this
  didn’t help because although alerts were generated, their investigation took
  longer than it took to complete the global rollout.
- **Canaries**. Rolling out changes to a small set of the entire
  infrastructure allows you to observe the impact in production. This step is
  absent from previous Google outages but is now a specific step.
  Unfortunately, although the canary deploy did show the problem, the rollout
  was not aborted due to a separate software bug.

The latest post mortem is the most detailed of any previous public root cause
analysis. It goes into detail about the multiple layers of protection which the
previous post-mortems do not, so it’s difficult to say whether these were just
not reported or if they have since been added. However, since Google is a
serious engineering organisation, you have to assume they have been working on
improving things since the last global outage of August 2015 and at least some
of the above improvements were introduced since then.

## How reliable is Google Cloud?

Google Compute Engine [guarantees 99.95%
uptime](https://cloud.google.com/compute/sla) which equates to 4 hours and 23
minutes of downtime per year.

Historically, I have had concerns about Google Cloud’s reliability because as
you can see from the above incident reports, the postmortems all look to have
similar root causes: software rollouts without sufficient staging, canaries and
testing.

However, anecdotally over the last ~12 months I have seen significant
improvement in reliability from the workloads we run on [App
Engine](http://www.cloudstatusapp.com/), [Compute
Engine](https://cloudplatform.googleblog.com/2015/01/automated-MongoDB-backup-verification-on-Google-Compute-Engine.html),
BigQuery and Google Cloud Storage at [Server
Density](https://www.serverdensity.com/). This is now backed up by the detail in
the recent post-mortem explaining the layers of defence in depth.

Indeed, the post mortem write up [has received generally good
comments](https://news.ycombinator.com/item?id=11489791) and only serves to
improve confidence in the service. When you have technical buyers, they want to
know the details of what went wrong because. Hiding behind a layer of secrecy
does not help.

Although a global outage is never good, I am more confident in Google Cloud
Platform than before this outage. And, contrary to the final statement at the
end of the post mortem about it being unusually detailed, I hope they continue
to publish full root cause analysis for the inevitable future outages!
