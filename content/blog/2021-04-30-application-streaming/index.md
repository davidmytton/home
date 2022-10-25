---
title: "How energy efficient is application streaming?"
date: 2021-04-30
modified: 2021-04-30
draft: false
tags: ["IT Energy", "Cloud", "Energy Efficiency"]
summary: "As more applications are run through a web browser, even that is 
beginning to be streamed from the cloud. Is that the best use of our now highly 
efficient computers? How energy efficient is application streaming?"
url: how-energy-efficient-is-application-streaming
---

Client / server architecture is back. The web browser has become the universal
client for everything we do.

Our email (GMail, Hey, Outlook Web), chat (Discord, Slack), video (Netflix,
Amazon Prime, YouTube), even highly complex applications like spreadsheets in
Google Sheets or design in Figma. If they’re not exclusively accessed through a
web browser, their desktop clients are built using web tech wrapped in Electron.

There are still a few applications which use native code – Apple’s Mail client
is one of my favourites, and Microsoft Office is best used through their desktop
apps – but only a minority have native desktop clients.

Streaming the browser itself is the next step. Run it in an isolated cloud
environment, and stream the output back to the client. A new
startup, [Mighty](https://www.mightyapp.com/), just announced such a product,
and [Cloudflare also has a similar
offering](https://www.cloudflare.com/en-gb/teams/browser-isolation/).

Why? Security is a big reason. Running everything through a browser means it
becomes a single point of attack for all your data. Vendors ship regular
updates, but how often do you keep your browser running with all those tabs,
ignoring the “update available” indicator?

Performance is supposed to be another reason. You might think that there would
be too much latency when streaming a browsing session, but with high broadband
speeds and the ability to locate the service in edge data centres close to the
user (Cloudflare has 200+ locations), the network performance challenge can be
mitigated.

If the service is run on high-spec servers and hardware accelerated, rendering
performance can also be improved. Mighty advertise how each instance is running
on powerful NVIDIA GPUs and gets 16 vCPUs and 16GB of RAM, for example.
Cloudflare’s service renders everything in the cloud, then ships the final
output back to the client.

## What about energy efficiency?

Consumer electronics have never been more energy efficient, especially laptops.
With battery power as a major buying criteria and energy efficiency standards
enforced by regulation, [the environmental impact of a consumer
laptop](https://davidmytton.blog/the-environmental-impact-of-buying-a-new-laptop-comparing-the-macbook-air-and-surface-laptop/) is
mostly in the manufacturing. Use-stage energy consumption is very low.

We are also at the beginning of a major CPU architecture transition. ARM chips
have been common in mobile devices for years, but Apple is now pushing its
desktop platform forward with the new M1 chips. These are more energy efficient
and higher performance than comparable desktop-class chips.

[The opposite is true for
servers](https://davidmytton.blog/carbon-footprint-laptops-vs-servers-intel-vs-arm/).
Energy consumption makes up most of their footprint, which is why there is so
much focus on the source of electricity generation for data centres. AWS is
several generations through its ARM Graviton chip and if more developers are
using ARM for their dev environment they may want the same in production, but
Intel (and to a lesser extent, AMD) is still dominant in server environments.

As we’re getting more energy efficient with our own computers, does this mean
we’re pushing applications to run on less efficient systems in the cloud? Is the
introduction of application streaming services like Mighty and Cloudflare
Browser Isolation a negative for energy efficiency and the environment?

## Questions for assessing energy efficiency

It is not currently possible to answer these questions. There are only two
services, one in closed beta (Mighty), both are proprietary and neither release
any data that would allow us to start to make an accurate assessment. Lifecycle
Assessment is a formal methodology which I’m not attempting to replicate here,
but we can consider some of the questions we’d need to ask to be able to analyse
their energy consumption.

- What tasks are being performed? Working on a large Figma canvas would be
  more intensive than reading a blog post. This has an impact on the compute
  required for rendering, resident memory sizes and bandwidth transferred. The
  workload would need to be instrumented on a host level to be able to compare
  like-for-like.
- What is the software layer? [Apple’s Safari browser is more energy efficient
  than
  Chrome](https://singhkays.com/blog/apple-silicon-m1-video-power-consumption-pt-1/),
  and what is the overhead of the virtualisation layer?
- What hardware components are being used? Mighty describes the processes as
  Virtual CPUs (vCPUs) which means they are not physically dedicated to each
  session and can be shared by other users. On a laptop, all the resources are
  dedicated 100% to the user regardless of whether they’re in use. Cloud
  services can allocate the processor time based on actual demand.
- How are tasks shared between CPU and GPU? The new M1 Macs are able to make
  use of integrated graphics and memory, which is a major reason for their
  huge performance improvements. Separating the architecture into distinct
  CPU, GPU and memory modules may mean less efficiency.
- What is the platform utilization? How often are you pushing your laptop to
  its limits? Probably not that often. And you aren’t using it 24/7. Platforms
  like Mighty and Cloudflare are always on and able to provide service to
  users all around the world. Utilization is a major factor in allocating
  lifecycle emissions, for example. Mighty is a new startup so probably has
  fewer users compared to Cloudflare who have a multi-product platform.
- What is the hardware refresh rate? Apple expects a laptop to last 4 years
  but servers often remain deployed for much longer. Refresh rates have a
  major impact on overall environmental footprint, but [deciding whether the
  efficiency gains are worth
  it](https://doi.org/10.1109/TSUSC.2018.2795465) is a complex topic.
- Not everyone has a highly efficient, brand new M1 MacBook. The best way to
  minimise the environmental footprint of your computer is to not buy a new
  one. If older systems can have their life extended by cloud streamed
  services, that can avoid manufacturing emissions.
- Where is the workload running? Is it in an edge data centre close to the
  user (low latency, less data transferred) or is it running in a larger data
  centre somewhere far away? Network data transmission has its own overhead,
  especially if you are on a mobile (4G or 5G) connection compared to
  fixed-line.
- What is the energy profile of the electricity powering the data
  centre? [“100% renewables” doesn’t actually mean that renewable electricity
  is powering the data
  centre](https://davidmytton.blog/how-data-center-operators-can-transition-to-renewable-energy/),
  so how is that being accounted for? What is the impact if you live in Norway
  (high renewables) but the data centre is in Germany (lower renewables)?

Whilst it might seem intuitive that using Safari on an M1 MacBook Air in Norway
is more energy efficient than streaming a web browser from the cloud, making a
robust assessment requires a lot of assumptions. The security tradeoffs may
outweigh the benefits of minimising energy consumption. And being able to burst
into the cloud for high-performance, GPU intensive workloads could be more
efficient than buying a high-spec desktop computer that is idle most of the
time.

The main challenge is that we cannot measure the impact. Publishing an energy
intensity figure would be helpful, as we’re starting to see in manufacturing
(e.g. kgCO2 per order) and telecoms (e.g. kgCO2 per GB), but that level of
reporting is a long way off for most. It will also be a moving target. Telecoms
is a large, slow-moving and capital intensive industry whereas software is
changing all the time. How relevant is an assessment of Mighty in 2021 when the
software (and some of the hardware) will likely be quite different in 18 months?

As you can see, there are a lot of variables!
