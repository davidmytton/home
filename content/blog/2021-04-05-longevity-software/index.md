---
title: "Longevity of software"
date: 2021-04-05
modified: 2021-04-05
draft: false
tags: ["Software"]
summary: "Services shipped with Windows 95 no longer work - ICQ, AOL Messenger, 
MSN. All shut down. But how likely is that today?"
url: longevity-of-software
---

Reading [Windows 95 — How Does it Look
Today?](https://dmitryelj.medium.com/windows-95-how-does-it-look-today-feda837922d9) made
me think about how few internet services have survived over the past 25 years.

When the author tested the browser built into Windows 95, the default URL –
home.microsoft.com – failed to resolve. This is a good example of how URLs
regularly change. At some point in the last 0-25 years, that URL was broken,
probably earlier than later. Broken references are [a problem in
academia](https://davidmytton.blog/dead-references/) even with documents that
have DOIs which are expected to remain available forever. They don’t.

Major websites like Google and Medium also didn’t work. We have become used to
building highly complex websites with all sorts of shiny new technologies. HTML
and CSS and JS and React and icon fonts and WebAssembly…layers upon layers upon
layers. This has allowed the development of sophisticated applications that can
work amazingly well in the browser, such as Google Sheets or Figma, but do we
need that advanced level of technology for everything?

What technology that we rely on today will simply cease to work in a few years?
This made me think about what services and platforms we use today that we
consider crucial to our everyday life. Facebook Messenger, Skype, WhatsApp,
WeChat, Twitter, Reddit, Signal, Slack. In 25 years I expect few of these will
exist. This is not an argument for ignoring progress, but more an observation
about how rapidly technology becomes obsolete.

This is why open protocols are important. Email is a good example of a
technology that was around 25 years ago, and will likely still be around in 25
years time. Why? It’s an open protocol. Anyone can build an email client, run an
email service, manage their own email servers. Clients have come and gone. GMail
is all mighty today, but new, innovative services are showing up.

This is because the core protocols still work fine. The Windows 95 post explains
how the author was able to connect to the internet (using TCP/IP), and ping
still worked. I bet a Windows 95 email client would work too.

The underlying technology might be moving rapidly, but what about the services
built on top of it? Services shipped with Windows 95 no longer work – ICQ, AOL
Messenger, MSN. All shut down. But how likely is that today? As the internet
scales and more and more people get locked into proprietary systems, perhaps it
is becoming harder and harder for new systems to displace the old:

> Leaving Facebook in the 21st century is like my grandmother leaving the USSR
> in the 40s: you can go, but your friends and loved ones are all held hostage
> befhind Zuckerberg’s Iron Curtain, so leaving Facebook means leaving your
> communities, your relationships. That’s not as hard as kicking opioids, but
> it’s not easy either. And your presence on Facebook is the reason someone else
> can’t go.
>
> <cite>[IP, Cory Doctorow](https://locusmag.com/2020/09/cory-doctorow-ip/)</cite>

It’s still possible for proprietary systems to be overturned – a sudden shift,
like with the WhatsApp Privacy Policy changes can help – but the power of
proprietary platforms operating at scale makes today quite different from 25
years ago.

[We don’t need more
platforms](https://world.hey.com/dhh/no-more-platforms-please-8f01445e), we
need [better
protocols](https://knightcolumbia.org/content/protocols-not-platforms-a-technological-approach-to-free-speech) (and [products
built on top of them](https://signal.org/blog/the-ecosystem-is-moving/)). This
is where government should focus their efforts – not on insignificant fines, not
on trying to break up companies that would likely have no effect. Government
regulation should stay away from the details of how tech companies operate and
act at a higher level by forcing an open approach to data, protocols and
networks. [Interoperability](https://stratechery.com/2021/the-webs-missing-interoperability/) is
the key that helps level the playing field.
