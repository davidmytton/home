---
title: "Sustainable dev environments in the cloud"
date: 2022-06-29
modified: 2022-06-29
draft: false
tags: ["Cloud", "Website Energy", "Energy Efficiency", "Programming"]
summary: "Is it better to replace powerful developer laptops with cloud dev 
environments? What is the carbon cost of my software development – builds, 
tests, deploys, code hosting, dev environments?"
canonicalUrl: https://www.devsustainability.com/p/sustainable-dev-environments-in-the-cloud
url: sustainable-dev-environments-in-the-cloud
---

A year ago [I considered the energy efficiency of application
streaming](https://davidmytton.blog/how-energy-efficient-is-application-streaming/) vs
running native, local applications. The technology being implemented by the
likes
of [Mighty](https://www.mightyapp.com/), [Cloudflare](https://www.cloudflare.com/en-gb/products/zero-trust/browser-isolation/),
and more hybrid options like [Whist](https://www.whist.com/), is still very
early so I was mostly asking questions.

All those questions remain. Until these companies provide detailed carbon
accounting for their products, it’s not possible to make comparisons, only
speculate. I also focused primarily on consumer use-cases like web browsing with
lots of tabs, or running heavy applications like Figma. With newer technologies
like WebAssembly allowing the browser to do even more, this is only going to
become more common.

A use-case I didn’t consider was that of software developers offloading
workloads to the cloud.

I have recently been setting up
a [devcontainer](https://code.visualstudio.com/docs/remote/containers) for the
codebase we’re working on for a new product at [Console](https://console.dev/).
This is a significantly better way of defining the runtime dependencies for
developers because rather than installing languages and frameworks locally –
which might conflict across projects – they can be self-contained and packaged
in the same way you would distribute and deploy the application itself. You can
then bootstrap the container against Docker running locally. Each branch can
have a different instance, it’s easy to reset, and you can keep everything
isolated.

With VS Code, the [Remote
Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) extension
allows you to run that container locally on Docker, or on a remote server
somewhere. [GitHub Codespaces](https://github.com/features/codespaces) is a
productised version of that. Prebuilds mean everything is ready to go when you
spin up a new Codespace. GitHub themselves have [moved all their development to
this
model](https://github.blog/2021-08-11-githubs-engineering-team-moved-codespaces/). [GitPod](https://gitpod.io/) is
an open source alternative.

![Screenshot of creating a new GitHub Codespace](create-codespace.png "Create a
new GitHub Codespace. Note how there are only 4 regions and the options are not
specific enough to know the precise location and estimate the carbon
intensity.")

Prior to configuring the devcontainer I was running everything on my M1 Macbook
Air. The performance is amazing – tests run in a few seconds and I have the
database, frontend and backend APIs, and the Firebase Auth emulator all running
locally. I can develop anywhere!

However, one of our team has an older laptop that wasn’t coping well in the
summer heat. It’s not even that old – 2018 – but still has all the fans running
to deal with the dev environment. In the past, the simple solution would be to
buy a new laptop. It was easy to justify buying the top spec because developer
time is so valuable, and they need to run VMs and tests and builds with minimal
lag. Today, developer time is even more valuable, but the decision is less
clear. It may be better to offload that processing to the cloud.

Instead of buying a brand new machine – [with all the carbon cost of that
purchase](https://davidmytton.blog/carbon-footprint-laptops-vs-servers-intel-vs-arm/),
plus all the time wasted setting up a new system – we decided to use it as an
opportunity to experiment with GitHub Codespaces. It took me an hour or two to
configure all the dependencies correctly, but now we have the entire environment
running in the cloud.

Not only have we saved the carbon involved with buying a new laptop, if we do
decide to buy one then the spec doesn’t need to be so maxed out. Cheaper in
dollars, but also cheaper in resources.

## Some remaining questions

It’s clear that physical resources were saved, but calculating the actual saving
is still not possible. I assume GitHub Codespaces runs on Azure, so
inherits [the work Microsoft is
doing](https://davidmytton.blog/fighting-over-who-has-the-greenest-public-cloud/) around
sustainable computing. But to what extent? You can’t find out precisely which
data center the environment is running in, so you can’t figure out the carbon
intensity.

Is the processing more efficient in the cloud? We assume so, but to what degree?
Could the savings from not replacing the laptop be offset by a more frequent
hardware refresh cycle in the data center? What resources are used by the
prebuilds? The Codespaces UI gives you a nice output showing the time saved
using them, but what about extra services, like [the GPUs that are
involved](https://twitter.com/NateTheFinch/status/1539384375137255425) if you
use GitHub Copilot where you get AI code suggestions every time you type
something?

It’s great that [you can now get carbon footprint data from all three cloud
providers](https://davidmytton.blog/cloud-emissions-transparency-stage-1-completed-what-next/),
but what about the services built on top of them? Now we need that carbon data
on a GitHub organization level. What is the carbon cost of my software
development – builds, tests, deploys, code hosting, dev environments?
