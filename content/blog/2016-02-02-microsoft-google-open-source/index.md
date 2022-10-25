---
title: "What's the real reason Microsoft and Google are releasing open source?"
date: 2016-02-02
modified: 2016-02-02
draft: false
tags: ["Cloud"]
summary: "Google and Microsoft might be generously helping the open source 
community, but there are real strategic reasons for their open source projects 
too"
url: whats-the-real-reason-microsoft-and-google-are-releasing-open-source
---

When individuals release open source projects, their motivations are often
altruistic. Their intention is to give back to the community, get as many people
as possible to help improve the project, or just to release what they think is a
useful tool to others.

Although the general perception of open source has definitely advanced
since [Microsoft's "un-American"
comments](http://www.salon.com/2001/02/15/unamerican/), the best companies are
not open sourcing things for the altruism. There are real, strategic reasons
hidden behind the warm and fuzzy glow of open source.

Google and Microsoft are good examples of this.

## Google Cloud and open source

Google has a major advantage when it comes to container tooling because it
effectively invented the concept and has been running containers in production
for almost a decade. As a result, Kubernetes is perhaps the most famous of
Google's recent open source releases. For the uninitiated, Kubernetes is a
cluster and container orchestration framework that allows you to schedule
workloads across many nodes.

The goal for this project seems to be to provide a standard platform for
deploying and managing containerized environments. Developers will build their
infrastructure using Kubernetes because it's free, and it has good
documentation, well-designed APIs, and a growing ecosystem.

This works well for experiments and personal projects, but [in the words of
AWS's CTO, Werner
Vogels](http://www.allthingsdistributed.com/2015/07/under-the-hood-of-the-amazon-ec2-container-service.html),
all this management is "undifferentiated heavy lifting" that you really should
be outsourcing to an experienced provider.

AWS has a massive head start with its huge cloud portfolio, but Google's
Container Engine happens to be what amounts to a hosted SaaS version of
Kubernetes. This means that if Kubernetes becomes the default way of running
containers, Container Engine could become the default managed, supported service
for it. Managed, supported services are things that businesses like.

The recently open sourced [Seesaw load
balancer](http://google-opensource.blogspot.co.uk/2016/01/seesaw-scalable-and-robust-load.html) follows
exactly the same approach. Sure, you can run the load balancer yourself, but you
can get the exact same functionality with Google Cloud Platform's load balancer
products. They come with elastic scalability, support, an easy-to-use-control
panel, and APIs.

Another Google project that may follow the same example
is [TensorFlow](https://www.tensorflow.org/), the machine learning framework.
This used inside Google's massively distributed data centers but the open source
version is limited to a single node. It seems inevitable that Google will
release an elastic machine learning service running on Google Cloud Platform
that utilizes TensorFlow.

## Microsoft and open source

Google's competitive advantage is its advanced infrastructure. Cloud Platform is
its attempt to productize that, and open source is a great way to drive
adoption. You can run it yourself, but a cheaper, easier and more flexible
approach would be to let Google run it for you.

Microsoft has a different approach. Azure may be ahead of Google in terms of
customer adoption but many would argue that Google has a much larger scale
infrastructure, it just hasn't effectively sold it to customers yet. This might
mean that people end up picking the open source library to build on because they
know they can eventually move the workloads over to the best platform (Google).

To counter all that, Microsoft has to provide a better open source option so
that people pick the product because it has the best features. They may or may
not decide to run it on Azure, but it reduces the chances that Google's platform
will become the default choice.

This is what we can see developing in [CNTK](https://github.com/Microsoft/CNTK),
a machine learning framework. [According to
Microsoft](http://www.wired.com/2016/01/microsoft-tries-to-one-up-google-in-the-open-source-ai-race/):

> CNTK has a big advantage over TensorFlow for people outside of academia: it
> can take advantage of the power of many servers at the same time. That's
> important because it's rare that a single computer is powerful enough to
> handle a real-world artificial intelligence application, such as speech
> recognition on an app used by millions of people. Internally, Google likely
> uses TensorFlow on thousands of servers at a time. But the version Google
> released to the public, Huang says, can't be used in this way.

This is important because Google considers its infrastructure to be a
competitive advantage and is probably why the restriction exists in the open
source version.

The next logical step for Microsoft would be to integrate it into its own [Azure
Machine Learning
service](https://azure.microsoft.com/en-us/services/machine-learning/). Indeed,
it [may already be more efficient to run CNTK on top of Azure's upcoming GPU Lab
product](http://blogs.technet.com/b/inside_microsoft_research/archive/2015/12/07/microsoft-computational-network-toolkit-offers-most-efficient-distributed-deep-learning-computational-performance.aspx).

It's no longer a race just to have the best proprietary cloud services. Open
source is a key strategy behind their adoption, especially for workloads that
evolve past personal projects into large scale commercial systems.

Who will get there first: Microsoft or Google?
