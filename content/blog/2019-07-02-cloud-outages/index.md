---
title: "What are the common causes of cloud outages?"
date: 2019-07-02
modified: 2019-08-08
draft: false
tags: ["Cloud", "Transparency"]
summary: "What causes cloud outages and downtime? Misconfiguration? Software 
bugs? Human error? A look at Amazon, Azure and Google clouds to see what causes 
downtime."
url: what-are-the-common-causes-of-cloud-outages
---

The argument for using cloud services goes along these basic lines:

1. The big 3 cloud providers (AWS, Azure, Google Cloud) [invest more money in
   their cloud platforms every
   quarter](https://www.platformonomics.com/2018/05/follow-the-capex-separating-the-clowns-from-the-clouds/) that
   you will ever invest in your infrastructure.
2. It is impossible to compete with the level of functionality, efficiency and
   security of the big 3 cloud providers for what are commodity IT services
   (compute, storage, networking), and the services built on top of them (e.g.
   databases, queues, email). The core offerings from the big 3 will always be
   best in class.
3. Running IT infrastructure is not a core expertise that needs to be owned to
   differentiate what your business offers to customers.

![Cloud provider capex](cloud-capex.png "Cloud provider capex from [Follow the
CAPEX: Separating the Clowns from the
Clouds](https://www.platformonomics.com/2018/05/follow-the-capex-separating-the-clowns-from-the-clouds/)")

As such, all IT services should be outsourced to one of the big 3. Which one you
pick will be more of a personal preference because they are mostly the same.

Trust their infrastructure but build your services using the usual
recommendations for redundancy and reliability i.e. deploying in multiple zones
and ideally multiple regions. [Be aware of the cloud tax that is
networking](https://davidmytton.blog/the-hidden-costs-of-cloud/).

There is basically no argument for not using cloud until you get to extreme
scale. Even then, only very specific use cases are worth considering – those
which give you a true competitive advantage.

Netflix is the best example here: almost all their infrastructure runs on
AWS, [except for their content
delivery](https://media.netflix.com/en/company-blog/how-netflix-works-with-isps-around-the-globe-to-deliver-a-great-viewing-experience) where
they have custom hardware. An example of a company making the wrong decision
here is Dropbox moving away from AWS.[Did they miss their
opportunity](https://stratechery.com/2019/the-new-dropbox-the-cloud-os-connecting-versus-file-sharing/) as
a result?

> That’s why I actually find this announcement really disappointing. Apparently
> Dropbox has been devoting significant resources for at least two years to a
> project that will no doubt have a positive impact on the bottom line but a
> minimal impact on the top line…How might have the product and company evolved
> if the company had continued to rely on AWS and devoted its resources to
> fixing its product-market-business model fit problem?
>
> <cite>[Dropbox Leaves AWS, Should UPS and Fedex Be
> Afraid?](https://stratechery.com/2016/dropbox-leaves-aws-should-ups-and-fedex-be-afraid/)</cite>

## Trusting the cloud

Inherent in the decision to outsource all of your infrastructure to a third
party cloud provider is that you must trust them to deliver. IT is mission
critical for most businesses so you want to be sure that they are going to do a
good job with the reliability of core infrastructure.

Any argument that assumes you can run your infrastructure more reliably than the
big 3 cloud providers can be countered by highlighting the above investment
numbers and then following architecture best practices: deploy across
multiple-zones and regions and test your failover plans.

Cloud infrastructure is a commodity in the same way that electricity and other
utilities are. Considering generating your own electricity is absurd. And if
your operations are so critical as to require backup electricity generation, the
cloud-native approach is to deploy across regions and [perhaps even consider
multi-cloud](https://www.usenix.org/conference/srecon18americas/presentation/chakrabarti).

That said, no complex system can achieve 100% uptime. You have to assume
failure, plan for it and test it.

So when things do go wrong, what are the common causes of cloud outages? What
causes cloud downtime?

## How do we know what causes cloud outages?

### What is a cloud outage?

First we need to define “outage”. Some define it quite simply:

> Cloud Outage simply refers to the duration when the cloud infrastructure
> service is unavailable for use. The unavailability may also refer to
> performance inadequacy of the service, as per the agreed SLA metrics.
>
> <cite>[What is a Cloud Outage? Cloud Outages
> Explained](https://www.bmc.com/blogs/cloud-outage/)</cite>

But it is actually more complex than that.

> Consider for example “monthly uptime percentage for a VM will be at least
> 99.99%.” How are we measuring uptime? On what granularity (seconds, minutes,
> calendar months, rolling 30 days,…)? What is ‘up’? The VM is provisioned? The
> VM is running an OS? The VM is reachable from the Internet? Is a performance
> brownout an outage? And so on.
>
> For cloud providers things get extra complicated due to multi-tenancy, and the
> fact that the behaviour of their clients can also impact SLIs. As a simple
> example, an SLO around network throughput might rely on the customer running
> software capable of driving the network fast enough. Or a system availability
> SLO, for availability seen by the end user, may well depend on the user
> carefully exploiting the available redundancy.
>
> Expressing available SLOs in terms of ‘nines’ also causes some issues: it
> hides the difference between many short outages and a few long ones, which is
> something many customers care about. It also treats all outages as equal,
> whereas an outage on Black Friday for a retailer is much worse than an outage
> on a quiet day of the year.
>
> <cite>[Nines are not enough: meaningful metrics
> for clouds](https://blog.acolyer.org/2019/06/19/nines-are-not-enough/)</cite>

### Methodology

For the purposes of this article I am going to look at the public post-mortems
published by the 3 big cloud providers (AWS, Azure and Google Cloud) since 2016
for their core compute, networking and storage services only.

I’m excluding other services from those cloud providers because because the
higher level services e.g. databases, will rely on these commodity low level
primitives. Compute, networking and storage are the lowest level services that
customers can build their own applications on.

The other cloud providers (e.g. Oracle, IBM, Alibaba) are not relevant because
they are so small. The only reasons to choose them are political.

In each case I will try to categorise each into 1 or more generalisable root
cause e.g. software bug or misconfiguratiom.

Cloud environments are complex so causes such as “a server failed” are highly
unlikely. Outages typically involve a cascade of failures with multiple systems.
Where possible I will try and find a single root cause category but it may be
multiple problems that ultimately resulted in the outage.

### Limitations

Cloud providers do not provide consistent reporting for their outages. They have
their own criteria for which ones get a public post-mortem, how detailed it is
and whether it covers everything that happened.

That means that this analysis is more anecdotal than scientific, but it should
hopefully be useful for understanding what the common root causes are.

## What causes cloud outages?

The data below shows that software bugs cause a majority of outages. Sometimes
this is due to poor testing but mostly it is due to race conditions or
unexpected situations triggering unusual code paths.

The actual number of outages is not important. I have not separated outages that
affected a single zone (more frequent) from those that might have brought down
the entire cloud platform (very rare). The lesson in the former case is to
architect your application properly.

More detailed analysis about what those software bugs are can be found in a
paper specifically analysing Azure – [What bugs cause production cloud
incidents?](https://people.cs.uchicago.edu/~shanlu/paper/hotos19_azure.pdf) ([or
a writeup of the paper
itself](https://blog.acolyer.org/2019/06/21/what-bugs-cause-cloud-production-incidents/)).

> Among all incidents caused by bugs, the most common causes are (1) incorrect
> or missing detection and handling of component failures (31 %) and (2)
> inconsistent data-format assumptions held by different software components or
> versions (21 %). Timing bugs are also common (13 %), with many of them related
> to conflicting accesses to not only in-memory data but also persistent
> resources. Finally, incorrectly set constant values are non-negligible (7 %)
>
> <cite>[What bugs cause production cloud
> incidents?](https://people.cs.uchicago.edu/~shanlu/paper/hotos19_azure.pdf)</cite>

Although this paper focuses just on Azure, engineering approaches are likely to
be similar amongst these industry-leading companies. This means we can assume a
similar situation at all cloud providers.

#### Outages before 2016

Given the speed of development of technology, I have limited my methodology to
looking at outages since 2016. However, there is more data available
historically such in the paper [Why Does the Cloud Stop Computing? Lessons from
Hundreds of Service
Outages](https://ucare.cs.uchicago.edu/pdf/socc16-cos.pdf) which looked at a
broad range of cloud outages from 2009 to 2015 across 32 different cloud
services.

### AWS Outages

AWS does not provide an easy to access history of public incident
post-mortems. [The AWS Post-Event Summaries
page](https://aws.amazon.com/premiumsupport/technology/pes/) only lists 2 major
outages since 2016 but this list is not exhaustive. For example, the “[Summary
of the AWS Service Event in the Sydney
Region](https://aws.amazon.com/message/4372T8/)” in June 2016 is not listed.

This lack of transparency makes it difficult to analyse the types of incident
that AWS deals with and so we cannot make any conclusions.

#### Incidents

- 2018-11-22 – [Amazon EC2 DNS Resolution Issues in the Asia Pacific (Seoul)
  Region (AP-NORTHEAST-2)](https://aws.amazon.com/message/74876/)  
   Root cause: misconfiguration.
- 2017-02-28 – [Amazon S3 Service Disruption in the Northern Virginia
  (US-EAST-1) Region](https://aws.amazon.com/message/41926/)  
   Root Cause: human error.
- 2016-06-04 – [AWS Service Event in the Sydney
  Region](https://aws.amazon.com/message/4372T8/)  
   Root cause: unexpected type of power outage.

### Azure Outages

Azure only provide [90 days of incident
history](https://status.azure.com/en-gb/status/history/) and do not offer unique
links to each root cause analysis.

#### Summary

- Misconfiguration: 3
- Resource exhaustion: 1
- Inconsistent data replication: 1
- Software bugs: 2

The sample size is small due to the public incident history limit. According to
the paper “[What bugs cause production cloud
incidents?](https://people.cs.uchicago.edu/~shanlu/paper/hotos19_azure.pdf)“,
40% of all incidents over a 6 month peweriod were caused by software bugs:

> In this work, we systematically studied all the high- severity production-run
> incidents during a recent span of 6 months in Microsoft Azure services, which
> cover a wide range of services including computation, storage, data
> management, data analytics, IoT, media services, etc., and identified software
> bugs as the most common cause of cloud incidents (close to 40%). We then did
> an in-depth study of all the 112 high-severity production incidents that are
> caused by software bugs.

#### Incidents

- 2019-06-14 – Virtual Machines and Virtual Networks (Management) – North
  Europe  
   Root cause: misconfiguration.
- 2019-05-22 – Service Management Operations – West Europe  
   Root cause: resource exhaustion.
- 2019-05-13 – Network Connectivity – Increased Latency  
   Root cause: inconsistent data replication
- 2019-05-02 – Network Connectivity – DNS Resolution  
   Root cause: misconfiguration, software bug.
- 2019-04-16 – Networking Degradation – Australia Southeast / Australia East  
   Root cause: misconfiguration.
- 2019-04-09 – Virtual Machines – North Central US  
   Root cause: software bug.

### Google Cloud Outages

#### Summary

- Human error: 3
- Misconfiguration: 12
- Resource exhaustion: 4
- Router failure: 1
- Software bugs: 19

#### Incidents

- [2019-06-02 – Google Cloud Networking Incident
  #19009](https://status.cloud.google.com/incident/cloud-networking/19009)  
   Root cause: misconfiguration, software bug.
- [2019-04-04 – Google Cloud Networking Incident
  #19007](https://status.cloud.google.com/incident/cloud-networking/19007)  
   Root cause: software bug.
- [2019-03-12 – Google Cloud Storage Incident
  #19002](https://status.cloud.google.com/incident/storage/19002)  
   Root cause: resource exhaustion.
- [2019-03-06 – Google Cloud Networking Incident
  #19005](https://status.cloud.google.com/incident/cloud-networking/19005)  
   Root cause: software bug.
- [2018-12-21 – Google Cloud Storage Incident
  #18005](https://status.cloud.google.com/incident/storage/18005)  
   Root cause: resource exhaustion.
- [2018-12-19 – Google Cloud Networking Incident
  #18019](https://status.cloud.google.com/incident/cloud-networking/18019)  
   Root cause: human error.
- [2018-11-05: Google Compute Engine Incident
  #18012](https://status.cloud.google.com/incident/compute/18012)  
   Root cause: software bug.
- [2018-10-11 – Google Cloud Networking Incident
  #18016](https://status.cloud.google.com/incident/cloud-networking/18016)  
   Root cause: misconfiguration, software bug.
- [2018-09-04 – Google Cloud Storage Incident
  #18003](https://status.cloud.google.com/incident/storage/18003)  
   Root cause: resource exhaustion.
- [2018-07-27 – Google Cloud Networking Incident
  #18013](https://status.cloud.google.com/incident/cloud-networking/18013)  
   Root cause: misconfiguration.
- [2018-07-17 – Google Cloud Networking Incident
  #18012](https://status.cloud.google.com/incident/cloud-networking/18012)  
   Root cause: software bug.
- [2018-05-16 – Google Cloud Networking Incident
  #18009](https://status.cloud.google.com/incident/cloud-networking/18009)  
   Root cause: software bug.
- [2018-05-02 – Google Cloud Networking Incident
  #18007](https://status.cloud.google.com/incident/cloud-networking/18007)  
   Root cause: misconfiguration, software bug.
- [2018-01-31 – Google Compute Engine Incident
  #18001](https://status.cloud.google.com/incident/compute/18001)  
   Root cause: misconfiguration.
- [2018-01-18 – Google Cloud Networking Incident
  #18003](https://status.cloud.google.com/incident/cloud-networking/18003)  
   Root cause: software bug.
- [2017-10-12 – Google Cloud Storage Incident
  #17005](https://status.cloud.google.com/incident/storage/17005)  
   Root cause: software bug.
- [2017-08-29 – Google Cloud Networking Incident
  #17002](https://status.cloud.google.com/incident/cloud-networking/17002)  
   Root cause: software bug.
- [2017-07-06 – Google Cloud Storage Incident
  #17002](https://status.cloud.google.com/incident/storage/17002)  
   Root cause: software bug.
- [2017-06-08 – Google Compute Engine Incident
  #17008](https://status.cloud.google.com/incident/compute/17008)  
   Root cause: misconfiguration, human error.
- [2017-04-05 – Google Compute Engine Incident
  #17007](https://status.cloud.google.com/incident/compute/17007)  
   Root cause: misconfiguration, software bug.
- [2017-03-15 – Google Compute Engine Incident
  #17006](https://status.cloud.google.com/incident/compute/17006)  
   Root cause: router failure.
- [2017-01-30 – Google Compute Engine Incident
  #17003](https://status.cloud.google.com/incident/compute/17003)  
   Root cause: software bug.
- [2016-10-13 – Google Compute Engine Incident
  #16020](https://status.cloud.google.com/incident/compute/16020)  
   Root cause: software bug.
- [2016-08-22 – Google Compute Engine Incident
  #16017](https://status.cloud.google.com/incident/compute/16017)  
   Root cause: power outage, software bug.
- [2016-08-05 – Google Compute Engine Incident
  #16015](https://status.cloud.google.com/incident/compute/16015)  
   Root cause: misconfiguration.
- [2016-07-16 – Google Compute Engine Incident
  #16013](https://status.cloud.google.com/incident/compute/16013)  
   Root cause: resource exhaustion.
- [2016-06-29 – Google Compute Engine Incident
  #16012](https://status.cloud.google.com/incident/compute/16012)  
   Root cause: misconfiguration.
- [2016-06-28 – Google Compute Engine Incident
  #16011](https://status.cloud.google.com/incident/compute/16011)  
   Root cause: software bug.
- [2016-04-11 – Google Compute Engine Incident
  #16007](https://status.cloud.google.com/incident/compute/16007)  
   Root cause: software bug.
- [2016-02-24 – Google Compute Engine Incident
  #16005](https://status.cloud.google.com/incident/compute/16005)  
   Root cause: software bug, misconfiguration.
- [2016-02-23 – Google Compute Engine Incident
  #16004](https://status.cloud.google.com/incident/compute/16004)  
   Root cause: misconfiguration, human error.
- [2016-02-23 – Google Compute Engine Incident
  #16003](https://status.cloud.google.com/incident/compute/16003)  
   Root cause: software bug.
- [2016-02-03 – Google Compute Engine Incident
  #16002](https://status.cloud.google.com/incident/compute/16002)  
   Root cause: misconfiguration.
