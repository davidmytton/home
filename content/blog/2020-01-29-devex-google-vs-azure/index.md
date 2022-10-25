---
title: "The importance of the developer experience – comparing Google Cloud Functions vs Azure Functions"
date: 2020-01-29
modified: 2020-01-29
draft: false
tags: ["Cloud", "Startups"]
summary: "In porting a project from Google Cloud Functions to Azure Functions, 
I found Microsoft's developer experience is a great example of attention to 
detail. What does that mean for startups selling to developers?"
url: the-importance-of-the-developer-experience-comparing-google-cloud-functions-vs-azure-functions
---

I have been a fan of Google Cloud for several years. At the company I founded,
Server Density, we migrated to Google Cloud in 2017 [because of the Cloud
Bigtable time series database
product](https://blog.serverdensity.com/time-series-data-opentsdb-bigtable/).
Although Google lags behind AWS and Azure in the size of the ecosystem and range
of products, what they have is well designed.

[I do not use any Google products
personally](https://davidmytton.blog/configuring-for-security-privacy-and-convenience/) –
I do not like Google’s ad business model and stance on privacy. However, I have
several Google Cloud Functions running as personal utility functions. One of
these runs each day, randomly selecting a highlight from a book I’ve read on my
Kindle. It then emails it to me as a “quote of the day”. This was a simple, fun
Python project as an alternative to paying for [Readwise](https://readwise.io/),
written back in March 2019.

When [Microsoft made their climate
announcements](https://blogs.microsoft.com/blog/2020/01/16/microsoft-will-be-carbon-negative-by-2030/) earlier
this month (the [Sustainability
Calculator](https://azure.microsoft.com/en-gb/blog/microsoft-sustainability-calculator-helps-enterprises-analyze-the-carbon-emissions-of-their-it-infrastructure/) in
particular), I decided it would be a good opportunity to try out Azure. Although
Google is further ahead in their environmental progress ([matching global energy
usage with purchases of renewables since
2017](https://static.googleusercontent.com/media/www.google.com/en//green/pdf/achieving-100-renewable-energy-purchasing-goal.pdf) vs
Microsoft pledging to achieve this by 2025), I also wanted to test the Microsoft
developer experience. I last worked as a developer with Microsoft technologies
when the terrible Windows Vista convinced me to switch to macOS in 2007. Things
are different now.

## The local development experience

When I wrote my quotes function in March 2019, there was no local development
experience for Google Cloud Functions. Google had no specialist IDE and there
was no emulator for local testing. This meant development was slow and tedious
because I had to deploy every change to production to test it. The [Cloud
Functions
Emulator](https://github.com/googlearchive/cloud-functions-emulator) was Node
only and it was [subsequently deprecated in favour of the Functions
Framework](https://cloud.google.com/functions/docs/release-notes#June_06_2019).

Contrast this to when I tried Azure Functions this month. Visual Studio Code has
a [complete development environment for Azure
Functions](https://docs.microsoft.com/en-us/azure/azure-functions/functions-develop-vs-code).
It includes a local development server, a real debugger, and integration into
Azure so you can manage and deploy functions directly from the IDE. This made it
very easy to get started and test my code. Minimal friction, saving hours of
tedious trial and error.

Google has progressed since then. There is a [VS Code extension for
Kubernetes](https://cloud.google.com/code/docs/vscode/) (but not Cloud
Functions) and the [Functions
Framework](https://cloud.google.com/functions/docs/functions-framework) has
expanded to support several of the languages supported by Cloud Functions,
including Python [in Jan
2020](https://github.com/GoogleCloudPlatform/functions-framework-python/releases/tag/v1.0.0).
But the experience is still not as slick as Microsoft.

## The “best cloud experience” strategy

When Google released Kubernetes and then Google Kubernetes Engine, their
strategy appeared to be: k8s is a well supported open source project and you can
run it yourself, but we will provide the best cloud environment for k8s if you
prefer someone to run and manage it for you. Amazon tried to get people using
their container management competitor ([ECS](https://aws.amazon.com/ecs/)) but
it wasn’t very good. Google’s strategy paid off and now
both [Amazon](https://aws.amazon.com/eks/) and [Azure](https://azure.microsoft.com/en-gb/services/kubernetes-service/) are
trying to compete with Google’s specialist hosted Kubernetes.

Despite the initial mistake, Google now appears to be adopting the same strategy
with the Functions Framework. This is a generic, open source framework that
allows functions to be run in multiple environments, including Anthos, knative
and locally, but they offer a superior managed experience through Cloud
Functions.

However, this burst of activity in the Functions Framework is in contrast to the
lack of major development on Cloud Functions itself. [The public
changelog](https://cloud.google.com/functions/docs/release-notes) shows very
little development over the past few years especially considering how rapidly
AWS Lambda and Azure Functions are building out functionality.

I had the same complaint [when I reviewed the major serverless platforms in
2018](https://davidmytton.blog/who-has-the-best-serverless-platform/). Lambda
and Azure Functions have continued to speed ahead but what is happening with
Google Cloud Functions?

## Attention to detail

Microsoft has a lot of nice touches to their Azure documentation including
light/dark/high contrast themes, clear indication of when the document was last
updated and an integration into Github. Anyone can view source and propose edits
to the page. The bottom of each page shows open and closed Github issues linked
to that page, so you can quickly report problems and see what issues others have
encountered. Participation is built in through the issue tracker. Google has a
feedback option for each page but where does it go once submitted? Users cannot
participate in the development of the platform.

The quickstart guides are where developers enter, but they only stay there
briefly. These guides need to up to date and work perfectly every time for all
supported platforms and languages. This is surprisingly difficult when the
product is developing quickly, but documentation needs to be part of the release
process – do the docs match the implementation? Product quality is correlated
with documentation quality.

Google is innovating with several of its open source projects. Kubernetes is the
leading example and Functions Framework seems to be going in the same direction,
but that is not being matched by development of the Cloud Functions product.
There is a disparity between how well Google’s documentation covers the various
supported languages and the entirely platform is significantly less advanced
than competitors.

## Developer experience principles

It is clear that Microsoft is investing heavily in being a cloud platform
company. [VS Code is a popular
product](https://redmonk.com/fryan/2017/05/09/visual-studio-code-a-home-for-all-languages/) and
the GitHub acquisition demonstrates the commitment to developers further. The
developer experience seems to matter a great deal, regardless of whether you are
using Microsoft technologies.

For companies building developer products, we can learn quite a lot from how
Microsoft is approaching things:

- Technical writers are just as important as software engineers. [Writing has
  to be a core company
  value](https://davidmytton.blog/writing-as-a-core-company-value/) but the
  best documentation writers are not necessarily (or usually) the best
  developers. You may think the best person to write documentation is the
  person who implemented the code, but that is not true. You need someone
  without assumed knowledge to make the same mistakes as new user. A technical
  writer will encounter all the “first-run” problems that make the difference
  to successful deployment.
- You will never spot every error so make it easy for the community to provide
  feedback. Making your documentation source public and inviting pull requests
  and issue submissions is not difficult. Microsoft has done a great job with
  embedded issue tracking into each documentation page.
- Update documentation as part of the development cycle. You wouldn’t deploy
  code changes that break tests so why would you deploy code changes that
  break documentation?
- The same applies to SDKs and libraries. Documenting the code with language
  examples is the first step but once you commit to building language SDKs
  then you are also committing to keeping them up to date. Nothing kills the
  developer experience like being unable to use functionality that isn’t yet
  available on your platform/language of choice.

The developer experience is basically sales for developers. Your goal is
adoption and this is achieved by removing friction. Just like focusing on SaaS
onboarding or optimising time to deployment, [it’s worth
$millions](https://blog.jsr.wtf/the-million-dollar-minute/) and is why it is
crucial to [own the full delivery
stack](https://davidmytton.blog/losing-it-in-the-last-mile-why-owning-the-full-delivery-stack-is-important/).
