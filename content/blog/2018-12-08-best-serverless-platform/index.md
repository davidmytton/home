---
title: "Who has the best serverless platform?"
date: 2018-12-08
modified: 2018-12-08
draft: false
tags: ["Cloud"]
url: who-has-the-best-serverless-platform
---

Back in August 2017 [I wrote a
post](https://read.acloud.guru/aws-lambda-vs-google-cloud-functions-vs-azure-functions-who-has-the-serverless-advantage-f6c2535e72f4) about: Who
has the serverless advantage? AWS Lambda vs GCP Cloud Functions vs Azure
Functions. We were three years into commercial serverless offerings and there
were still a lot of limitations. My main observation was:

> What really matters is the availability and consumption of other services
> within the cloud provider ecosystem.
>
> Being able to execute functions in response to events is only as useful as
> what you can actually do within the execution pipeline. This is where the
> services differ — their ability to to pass data to backend services, perform
> calculations, transform data, store results, and quickly retrieve data.
>
> AWS benefits from being the leader in cloud by the sheer size of its product
> portfolio. The core services of compute, storage and networking are
> commodities — the differentiation is what’s built on top of them.

At the time, Azure Functions and AWS Lambda were similar in functionality and
significantly ahead of Google Cloud Functions, which was still in Beta. So how
have things progressed for each provider since then, and what does this say
about their approach to serverless?

## AWS Lambda

It is an interesting coincidence that both Alexa and Lambda were released in Nov
2014, which suggests that the requirements of one product may have influenced
the other. Alexa, a deployed on the Echo devices and in other hardware, in an
inherently event-driven product. It is only doing things when you trigger it. It
fits the Lambda execution model exactly.

If we assume AWS created Lambda to service Alexa as the first customer, this is
important because it means the product development is driven by internal
stakeholders who provide the initial demand and use case validation well in
advance of input from the general market, rather than copying competitors.

Given how well formed Lambda was on release, I think this is a reasonable
assumption. The continued development of the product since 2014 means it has a
significant headstart, and the internal use case meant there was always an
incentive to invest even in advance of adoption by external customers.

This means that Lambda essentially had no competition for 2 years until Azure
Functions and Google Cloud Functions came out in 2016, and Google wasn’t really
in the game until March 2017 due to the gap between the Feb 2016 Alpha and March
2017 Beta.

Today, Lambda supports runtimes in Java, Go, PowerShell, Node.js, C#, Python,
and Ruby and has added complex functionality such as [Step
Functions](https://aws.amazon.com/step-functions/) and integration into other
AWS products. Many other AWS products generate events which can be processed in
Lambda which is proving how you can tie together the full ecosystem to deal with
logging, metrics and security in particular. The original Alexa use case is
still valid, but many of these improvements are clearly driven by external
customers.

[Lambda@Edge](https://aws.amazon.com/lambda/edge/) is also interesting because
it allows you to execute your functions in CloudFront CDN locations, allowing
for low latency applications close to the user. However, it does have [some
major
limitations](https://medium.com/buildit/a-b-testing-on-aws-cloudfront-with-lambda-edge-a22dd82e9d12) (such
as 1MB response limits and a maximum of 25 deployed functions) so is clearly
still an immature product. But what we know about AWS suggests this will
progress rapidly. [As nicely visualised by
CloudZero](https://www.cloudzero.com/blog/our-take-on-the-new-stack-survey),
serverless is truly a spectrum:

![Illustration of serverless spectrum](spectrum-watermark.jpg "Serverless spectrum. From [Cloudzero](https://www.cloudzero.com/blog/our-take-on-the-new-stack-survey)")

## Azure Functions

Azure offers very similar functionality when compared with Lambda, with more
language support in [experimental
runtimes](https://docs.microsoft.com/en-us/azure/azure-functions/supported-languages) e.g.
Bash and PHP.

A big difference is the availability of [on-premise
functions](https://docs.microsoft.com/en-us/azure/azure-functions/functions-runtime-overview),
where you can run the workers wherever you wish (so long as you have a Windows
server). Until the recent release of [AWS
Outposts](https://aws.amazon.com/outposts/), this was a major difference in
product philosophy between AWS and Azure. The former was focused on pure cloud,
with functionality to help you move there whereas the latter adopted a hybrid
approach from the beginning. This makes sense for Azure given Microsoft’s
history of on-premise software. Now we see AWS expanding to try and include the
relatively small but still significant share of workloads which will always run
on-premise.

[A famous use case for Azure
Functions](https://www.troyhunt.com/serverless-to-the-max-doing-big-things-for-small-dollars-with-cloudflare-workers-and-azure-functions/) is
Troy Hunt’s [Have I Been Pwned](https://haveibeenpwned.com/) (HIBP) project,
entirely delivered using Cloudflare (who have their own serverless product,
covered below) and Azure.

But it’s not just functions being used – as I mentioned in the original article,
the rest of the Azure product portfolio is just as important. [HIBP makes
extensive use of Azure Table
Storage](https://www.troyhunt.com/working-with-154-million-records-on/), which
you could call another “serverless” product because it is a database as a
service – no need to deal with running SQL Server. This is where AWS has often
had a lead in the past because of the range of products they have. That’s less
relevant today because both Azure and Google have products in all the key areas:
storage, compute and databases.

## Google Cloud Functions

GCF has only been Generally Available since July 2018 which makes it the
youngest platform of the major three. However, it has actually been available in
public since 2016. This is something I’ve called App Engine Syndrome in the
past:

> Cloud Functions seems to be suffering from App Engine syndrome — big
> announcements of Alpha/Beta features, followed by silence/minimal progress
> until the next big announcement the following year. The focus of Google’s
> serverless ambitions seems to be Firebase, not Cloud Functions.

The [release notes](https://cloud.google.com/functions/docs/release-notes) show
regular updates and new functionality during the beta but there was nothing
between July 2018 and November 2018.

This is somewhat frustrating because at [Server
Density](https://www.serverdensity.com/) we made extensive use of Google Cloud
Platform and it is my preferred vendor of the big three – they have the best
console UX, documentation and APIs, and I’ve found all their GA products to be
well designed and robust.

Indeed, GCF is a good product that is easy to work with through the command line
and console. It has good integration into the rest of GCP whether as direct
triggers, through pub/sub, storage, monitoring and most recently [scheduled
functions](https://cloud.google.com/scheduler/docs/tut-pub-sub). The lack of
development on the core product is somewhat misleading because of how it
continues to be built into the rest of the platform, but it is concerning that
the development velocity of what is a growing technology in the industry is
seemingly being neglected. At least publicly, and in comparison to the rapid
progress of AWS Lambda.

My criticism of Google Cloud has long been that not enough of Google’s own
products use it. Of course, they use the underlying technologies and the
physical infrastructure, but unlike Amazon.com using AWS for their critical
retail operations, it is unclear how much of Google is using the same platform
that GCP customers are using. If Google had a use case similar to AWS and Alexa,
that might provide incentives to increase the velocity of development in
addition to any GCP customers. Maybe they do. But we still see [Google falling
further and further
behind](https://stratechery.com/2018/awsreinvent-and-outposts-aws-and-machine-learning-youtube-retreats-on-premium-video/).

## Other platforms

AWS, Azure and Google have the position of being the main three cloud providers.
Indeed, they are the only ones that matter for general use cases. Their
advantage is the vast resources each company can invest in infrastructure and
product development. However, that doesn’t mean they are the only players in
serverless. There are other, specialist providers who have particular use cases
in mind.

### Cloudflare Workers

I mentioned Cloudflare in the context of Have I Been Pwned above. Whilst all of
the main processing for HIBP happens on Azure, [over 99% of traffic is actually
being served by Cloudflare’s
CDN](https://www.troyhunt.com/serverless-to-the-max-doing-big-things-for-small-dollars-with-cloudflare-workers-and-azure-functions/) and
their [Workers](https://www.cloudflare.com/products/cloudflare-workers/) product.

Moving caching and request response serving to the edge reduced HIBP’s cost from
$9 per day to $0.02 per day. This was not just by being able to serve many
requests within Cloudflare’s free tier but also by eliminating almost 500GB of
Azure network traffic:

### StackPath EdgeEngine

As HIBP shows, avoiding network traffic is a second order benefit of using
serverless. Colocating other services on the same platform eliminates a large
amount of traffic so all you need to deal with is internal networking.
Serverless certainly means not having to deal with scaling server infrastructure
and so spending only based on what you use. But it also means that where you use
other products like CDN, you can avoid costly traffic back to the origin.

This is a big part of the use case for why we
launched [EdgeEngine](https://www.stackpath.com/services/edgeengine/) at
StackPath – we have huge volumes of CDN traffic where we serve as the edge
delivery provider, but requests still have go to back to the origin for dynamic
processing. One of the major selling points of StackPath CDN is the diversity of
PoP locations around the world. Your origin might be in AWS US East but if you
are serving traffic to Spain, you will still have a significant volume of
requests needing to go back to the centralised cloud provider.

Network costs at cloud providers are one of the biggest hidden taxes on using
public cloud, especially if you use third party services like a CDN. So if you
can eliminate those requests entirely you can not only provide better
application latency but also save on your bill. Now we have
our [EdgeEngine](https://www.stackpath.com/services/edgeengine/) product, [you
can do things like API token
validation](https://blog.stackpath.com/handling-jwt-validation-at-the-edge-using-serverless-edgeengine) without
it ever having to hit that central infrastructure.

## AWS Lambda vs Azure Functions vs Google Cloud Functions

Lambda created the market for serverless and continues to innovate and lead on
functionality. It benefits from the vast AWS product portfolio so is often a
default choice for those already on AWS.

Azure Functions are just as mature as Lambda. It’s the Lambda equivalent for
Microsoft fans, so is an easy default if you use Azure. .NET languages are well
supported, as you would expect.

Google Cloud Functions still has the same problems of slow product development
but the overall platform portfolio has improved significantly. It’s likely to
the first choice for developers starting from scratch, just because the overall
experience of working with Google Cloud is better than AWS or Azure. Google is
also innovating in other areas, such as with the Cloud Spanner database product.
GCF may benefit from those who want something in the platform they chose for
other reasons.

Ultimately, serverless is not just about functions. If you want more than just
simple request manipulation or one time processing then you need to be able to
connect to a datastore and other services like logging and monitoring. It’s been
possible to build full applications using only serverless, like HIBP, for a long
time. How sophisticated those applications get will now depend on what other
services appear to support serverless functions, and what the role for low
latency edge deployment plays in adding to the use cases. To quote Troy Hunt of
HIBP:

> So, in summary, the highlights here are:
>
> 1. Choose the right storage construct to optimise query patterns, performance
>    and cost. It may well be one you don’t expect (as blob storage was for me).
>
> 2. Run serverless on the origin to keep cost down and performance up. Getting
>    away from the constraints of logical infrastructure boundaries means you
>    can do amazing things.
>
> 3. The fastest, most cost-effective way to serve requests is to respond
>    immediately from the edge. *Don’t hit the origin server unless you
>    absolutely have to!*
>
> <cite>[Troy
> Hunt](https://www.troyhunt.com/serverless-to-the-max-doing-big-things-for-small-dollars-with-cloudflare-workers-and-azure-functions/)</cite>
