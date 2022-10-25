---
title: "You don’t need to be an expert to integrate AI in your startup"
date: 2017-08-13
modified: 2017-08-13
draft: false
tags: ["Startups"]
url: you-dont-need-to-be-an-expert-to-integrate-ai-in-your-startup
---

_Originally [published on The Next
Web](https://thenextweb.com/contributors/2017/08/13/dont-need-expert-integrate-ai-startup/)._

We’re used to hearing that AI and machine learning is hopelessly complex,
impossible to implement quickly, and that if you want to get on board the
machine learning bandwagon you’ll need to invest heavily in PhDs, specialists
and expensive experts.

This way of thinking is simplistic and behind the times: machine learning is a
broad set of technologies, and over the past few months and years there have
been huge strides in making machine learning’s benefits much more accessible to
startups, scale ups and lone developers alike.

Over the past few months I’ve spent a great deal of time investigating, learning
about and iterating on a number of different machine learning technologies to
take advantage of the vast quantities of time series data we have about
infrastructure performance from my company’s product.

We’re collecting billions of metrics every data from hundreds of thousands of
systems, all of which can be used to understand patterns and make future
predictions. Read on for some easy, actionable advice on how to get started from
scratch with machine learning — it’s easier than you think!

## Avoid TensorFlow — for now

Google made headlines in 2015 by open-sourcing TensorFlow, their internal AI and
machine learning framework. Released as an open source project, TensorFlow is
following the same strategy as Kubernetes — provide such a good product that it
becomes the industry standard, and offer a hosted, managed cloud version for
those who don’t want to maintain it themselves.

You can run TensorFlow workloads yourself but Google’s [Cloud Machine Learning
Platform](https://cloud.google.com/products/machine-learning/) offers a much
more optimised version, running on proprietary TensorFlow Processing Unit
chipsets. The strategy is all about making Google Cloud the best choice for
these jobs.

However, popularity can be deceptive and based on my personal experience
TensorFlow is often not the best solution for startups and small companies.
TensorFlow is great in that you get a high degree of control over your project
but that control comes at a cost. TensorFlow is a framework, and we’ve found it
requires significant data science knowledge and a lot of trial and error in
building, iterating and improving your models.

It’s not a toolset you should pick up if you’re after easy results or
plug-and-play functionality. Unless you’re a big corporation (which we’re not)
or have the budgets to hire data scientists to get into model development, it
might be tricky to secure enough budget to invest in TensorFlow from the start,
so you’d be much better trying more simplistic managed solutions first.

## The rise of ‘machine-learning-as-a-service’

For companies just starting out, the best place to begin is looking at the
managed service solutions from the likes of Amazon, Microsoft and Google. These
solutions are much more accessible to generalist teams, and companies that use
them get the benefit of vendors updating them and improving service over time.
Indeed, your own datasets help to improve the models!

This is because the larger the training data set, the more accurate the models
can be. Anyone can play with theoretical models but the truly interesting work
comes out of having real data, and this is an advantage the big players have
even before they add your data into the mix.

We’ve found that [Amazon Machine
Learning](https://aws.amazon.com/machine-learning/) is a great place to start.
AML differs from TensorFlow in a number of ways: with TensorFlow, you build your
own models and can then execute them against your datasets wherever you like
whereas AML requires you upload your dataset to Amazon then use their API to
execute queries. The downside is you don’t get to control the models and can’t
see into the workings of the system – you rely on Amazon to get it right. This
“plug and play” type approach but is less customised and flexible, so you may
end up needing replacing it with something more specialist in the future.

If you need a very particular type of functionality — detecting items in a
video, speech to text or translation, then there are specialist services from
all the cloud providers. These services use machine learning behind the scenes,
but you don’t need to think about it — send over the item for analysis and get
the results through an API. These APIs are quite specific and so if they do a
good job, you can just leave them to get on with it. It’s unlikely you’ll want
to customise them enough to make it worth starting from scratch.

Outside of the big three cloud providers, there are a host of technology
startups including Algorthmia, BigML and MLJar aiming to offer machine learning
through an API or SaaS application.

## Put your use cases first

I’ve seen many companies make the mistake of rushing into machine learning
without having a clear use case in mind, and this is a significant error. There
are robust ecosystems around each of the above ‘MLaaS’ platforms, and so you’ll
need to have awareness of the APIs available to you. Tools like [Amazon
Polly](https://aws.amazon.com/polly/) (text to speech) or the [Google Cloud
Video Intelligence
API](https://cloud.google.com/blog/big-data/2017/03/announcing-google-cloud-video-intelligence-api-and-more-cloud-machine-learning-updates) deliver
specialist functionality without requiring a high degree of knowledge as a
prerequisite.

Since they are offered as an API, you can mix and match across providers and
even test which does a better job where the service is the same. Most people
will probably stick with the cloud platform the rest of their infrastructure is
hosted on, but that’s not always necessary (data transfer cost and latency may
become an issue once you hit scale though).

At my company, we’ve been migrating from IBM Softlayer to Google Cloud and the
data transfer fees of (encrypted) traffic across the internet is part of the
total cost consideration, and an incentive to complete the move quickly! Once
it’s all within Google’s network then the lower (or zero) data fees apply when
using their services, and Google is widely considered to have well designed
machine learning capabilities.

I’ve found the advantage of using machine learning as a service APIs is that any
developer can pick them up and start playing. Serious machine learning with
TensorFlow requires a lot of time and real data science knowledge, which may be
worth investing in over the long term. However, to get something up and running
quickly and test the value proposition to your users, there are a variety of
options.

I’ve had a lot of fun testing out the different machine learning APIs and
solutions out there, and this element of fun and discovery makes it much easier
to lead a team on a small exploratory project. I’ve also found that implementing
something like Google’s 20 percent time, or even an internal hackathon could
also be a good opportunity to get everyone focused on building an initial
prototype.

Machine learning is a very over-hyped set of technologies — it’s currently
ranked by Gartner as [a buzzword](http://www.gartner.com/newsroom/id/3412017),
at the very top of their peak of inflated expectations. However there’s a
vibrant set of technologies under this umbrella term, and you don’t necessarily
need to have a highly-specialised workforce to take advantage of them. Start
small, use the managed services provided by the big tech firms, and you’ll be
surprised by how far you can go.
