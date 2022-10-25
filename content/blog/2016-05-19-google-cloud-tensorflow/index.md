---
title: "Google's cloud strategy becomes clearer with TensorFlow"
date: 2016-05-19
modified: 2016-05-19
draft: false
tags: ["Cloud", "Startups"]
url: googles-cloud-strategy-becomes-clearer-with-tensorflow
---

_Originally_ [_written for
InfoWorld_](https://www.infoworld.com/article/3072569/googles-cloud-strategy-becomes-clearer-with-tensorflow.html)_._

For years, one of Google's biggest differentiators has been its global
infrastructure. It has closely guarded its technologies, networking, and the
data centers. This has allowed it to announce revolutionary features like the
massive storage Gmail launched with, real time collaboration in Google Docs, and
super-fast Web search well ahead of competitors.

These innovations all come from running highly efficient infrastructure at
massive scale, something few of its competitors could match. However, with the
rise of cloud computing, such advantages have started to disappear.

Google's response was to start productising its internal technologies, and
Google Cloud Platform was born. Although very late to the party, Google has been
rapidly building its portfolio of cloud products. It's [differentiating through
operational
simplicity](https://davidmytton.blog/aws-vs-google-cloud-flexibility-vs-operational-simplicity/),
and although it offers commodity services like compute and storage, it sets
itself apart with managed services like databases, global load balancing, and
container management.

Google Cloud certainly has some [interesting compute
features](http://www.forbes.com/sites/janakirammsv/2016/05/09/five-unique-features-of-google-compute-engine-that-no-iaas-provider-could-match/) like
sustained discounts, pre-emptible instances, and live migration, but in essence,
anyone can offer compute as a service. The real reason to use any of the big 3
cloud providers (AWS, Azure, and Google) is their supporting portfolios.

Indeed, it's the services that couldn't be provided by anyone else that really
stand out, particularly when it comes to large scale databases. Google's
BigQuery is a great example of this because of the speed at which it can execute
queries across huge datasets. Google [provided an example of this when it
demonstrated executing a 30-second query across 3000+ cores as a small
job](https://cloud.google.com/blog/big-data/2016/02/understanding-bigquerys-rapid-scaling-and-simple-pricing),
and it has been [backed up by customers like
Spotify](https://twitter.com/mpjme/status/702167231623516160).

These services are built from the experience Google has gained building large
scale software systems over the years. But they're experts at hardware too, and
this is at the heart of Google's open source strategy.

As a tool to manage container clusters, Kubernetes was perhaps the first
important cloud framework to come out of Google. It's an open source
implementation of [Google's internal management
systems](http://queue.acm.org/detail.cfm?id=2898444) released to the world for
free. The goal is to standardise the APIs regardless of which platform they run
on so. Of course, you can run your own Kubernetes cluster but Google is betting
that you don't really want to do that kind of undifferentiated heavy lifting,
and instead will use a managed service to do it for you. A service that Google
Cloud Platform happens to offer!

This is a clever strategy to leverage open source to create standards whilst
supplementing it with a service that can do it all for you more efficiently and
with less operational overhead. Kubernetes and Google Container Engine were the
first example of this but with [the announcement of Google's new Tensor
Processing Units (TPU) at Google
i/o](https://cloudplatform.googleblog.com/2016/05/Google-supercharges-machine-learning-tasks-with-custom-chip.html),
we have another example. One that is even harder for competitors to replicate.

[TensorFlow](https://www.tensorflow.org/), Google's machine learning framework,
was open sourced at the end of 2015 as a standardised way to build deep learning
models. Following the exact same playbook as Kubernetes, the goal is to
standardise machine learning on a single framework and API. Of course, you can
run your own TensorFlow models but [Google now has a cloud
service](https://cloud.google.com/ml/) where you can run them instead.

Not only that, but the TPU announcement demonstrates that Google has optimized
dedicated hardware designed specifically to "deliver an order of magnitude
better-optimized performance per watt for machine learning." This is a true
differentiator because nobody else offers such a service on their cloud platform
and with the increasing focus on AI and machine learning, positioning Google
Cloud as the best place to run machine learning workloads is important.

Amazon and Azure are still very much in the lead when it comes to cloud services
overall, but it is becoming clearer how Google is differentiating its services.
This is a long game and you could argue that the war around compute and storage
is no longer interesting. What is interesting is Google's work on becoming a
platform for machine learning and AI, whether on the consumer side with the
other i/o announcements like [Allo and
Assistant,](http://9to5google.com/2016/05/18/allo-is-googles-new-messaging-app-with-assistant-built-right-in-expressive-features-and-more/) or
the developer side with TensorFlow and TPUs.
