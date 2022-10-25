---
title: "Will Spotify be to Google Cloud as Netflix is to AWS?"
date: 2017-03-04
modified: 2017-03-04
draft: false
tags: ["Cloud"]
url: will-spotify-be-to-google-cloud-as-netflix-is-to-aws
---

Almost exactly a year ago, we heard that Spotify was working on a huge migration
over to Google Cloud. They got off to a great start with a series of blog posts
about their use of Google Cloud Pub/Sub, [which I used to
calculate](https://davidmytton.blog/how-much-is-spotify-paying-google-cloud/)
what they might be paying if they were being billed at list price.

I had hoped [Spotify would blog](https://labs.spotify.com/) more about their
migration but we have heard about some other big converts to Google
Cloud, [Evernote being a good example with a detailed technical writeup of their
move](https://blog.evernote.com/tech/2017/02/08/part-1-evernote-service-options-migrate-google-cloud-platform-gcp/).
And of course we always knew Snapchat was running on Google, but [recently saw
their actual
spend](http://www.zdnet.com/article/snapchat-spending-2-billion-over-5-years-for-google-cloud/).
No doubt there will be some interesting case studies announced at GCP Next in
San Francisco next week.

That said, Spotify have not been entirely silent. Indeed, they have announced a
few interesting tools which indicate they’re beginning to build up a suite of
projects to help augment Google Cloud. This started with a writeup of [how they
built a custom system to manage compute
instances](https://labs.spotify.com/2016/03/25/managing-machines-at-spotify/),
but no code was released publicly. Then last month, [2 new open source projects
were announced around security and
compliance](https://labs.spotify.com/2017/02/22/google-cloud-security-toolbox/).

Netflix is perhaps the best example of being a leader in developing tools for
AWS. They are famous for running almost their entire business on AWS (except for
CDN) and [have had a strong set of open source projects for many
years](http://techblog.netflix.com/2015/10/evolution-of-open-source-at-netflix.html).
By building internal tools needed to run their systems on AWS, then releasing
them, they make it much easier for other businesses to adopt AWS. Netflix is
showing how to properly design cloud architecture and releasing tools so others
can follow their example.

This is a huge competitive advantage for AWS because if you have to pick between
platforms, the one with the biggest ecosystem, most shared knowledge and largest
pool of experienced engineers is often going to win. Google was very late to the
game and whilst it has a strong developer community in aggregate, the Google
Cloud specific ecosystem is very small.

Kubernetes is a great example of Google leading open development efforts with an
underlying strategy of getting people onto Google Cloud. Kubernetes is open
source but the managed service is Google Container Engine, which is the best
place to run your Kubernetes clusters. Google certainly has the resources to
jump start an ecosystem, but there’s more credibility when you have a big
customer leading instead.

With Spotify releasing its first 2 open source projects, I wonder if they will
become the Netflix of Google Cloud. This title is open right now. Perhaps it’ll
be Evernote. Or maybe Snapchat, after all they have been using GCP for longer.
