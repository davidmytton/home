---
title: "Technology vs philosophy, or macOS vs Linux"
date: 2021-02-21
modified: 2021-02-21
draft: false
tags: ["Hardware", "Software"]
summary: "I now have to make a decision between having the best, cutting-edge 
hardware vs the freedom and control to do what I want with the device I spend 
most of my time on."
url: technology-vs-philosophy-or-macos-vs-linux
---

Prior to the release of the new Apple Silicon MacBooks, Apple appeared to have
lost interest in the Mac. The terrible laptop keyboards [had only just been
fixed](https://www.theverge.com/2020/5/4/21246223/macbook-keyboard-butterfly-magic-pro-apple-design) and
macOS Catalina was the buggiest release in a long time. I struggled with
constant crashes and bugs throughout the system to the point where I decided to
move away from key Apple apps I had been using, [like
Notes](https://davidmytton.blog/the-best-note-taking-apps-for-mac-markdown-open-format-cross-platform/).

The announcement of macOS Big Sur was the final straw. Its [poor
UX](https://www.andrewdenty.com/blog/2020/07/01/a-visual-comparison-of-macos-catalina-and-big-sur.html) and [Apple-service-bypass](https://blog.obdev.at/a-hole-in-the-wall/) of
user-installed firewalls made me decide not to upgrade, and by the end of 2020 I
had switched to a [Star Labs
LabTop](https://starlabs.systems/pages/labtop-mk-iv) running Linux. I still have
my MacBook Air, but it may be the last Mac I own, and I have no intention of
upgrading it to Big Sur.

Despite this, Apple is the most innovative hardware company in consumer
technology. The new Apple Silicon MacBooks might look exactly the same ([still
with awful
cameras](https://www.wsj.com/video/series/joanna-stern-personal-technology/laptop-webcam-showdown-macbook-air-dell-xps-theyre-pretty-bad/415D393C-4320-442B-974D-1887E20C057F))
but the internals are a game-changer. The M1 chip
is [faster](https://twitter.com/dhh/status/1355904820746530816), [quieter](https://daringfireball.net/2020/11/the_m1_macs),
and more energy efficient than anything else on the market. Rosetta 2 is a real
marvel, with
emulation [reportedly](https://www.macrumors.com/2020/11/15/m1-chip-emulating-x86-benchmark/) performing
better on the M1 vs their native x86 versions.

Apple also has [the best platform
security](https://support.apple.com/en-gb/guide/security/welcome/web). From the
secure enclave on iOS devices and T2 macs through to native full-disk
encryption, privacy-by-design, and ongoing improvements such as the [iMessage
blastdoor](https://googleprojectzero.blogspot.com/2021/01/a-look-at-imessage-in-ios-14.html),
Apple has a real advantage being able to [vertically integrate the
stack](https://tidbits.com/2021/02/18/apple-platform-security-guide-reveals-focus-on-vertical-integration/).

Unfortunately, this means handing over more and more control to Apple. An
example of this was [the system integrity checker
outage](https://tidbits.com/2020/11/13/apple-network-failure-destroys-an-afternoon-of-worldwide-mac-productivity/) that
prevented users launching apps back in 2020. Or the deprecation of kernel
extensions in favour of a new API that prevented firewalls from operating
properly ([only now reversed in macOS
11.12](https://blog.obdev.at/a-wall-without-a-hole/)). Or the [locked down
system
volumes](https://eclecticlight.co/2020/09/12/what-could-go-wrong-with-apps-on-big-sur-and-apple-silicon/) which
are [hampering
backups](https://www.shirtpocket.com/blog/index.php/shadedgrey/thats_big_sir_to_you/) and
dual booting.

Linux has come a long way, particularly on the desktop where I’ve been using it
every day for the last 5 months. I rarely have to go back to my MacBook for
anything. I’ve encountered few bugs, it never crashes, it’s fast, all the apps I
need are available (desktop, command line, or via the web) and it’s all open
source. I have customised the UI and set up [a tiling window
manager](https://swaywm.org/) with a range of shortcuts that make my usage much
more efficient.

![Screenshot of my Linux desktop](../../iuse/desktop-2020-12-31.png "[My Linux
setup](https://davidmytton.blog/iuse/) as of 2020-12-31.")

I’ve never had an Apple device fail but my current MacBook Air has already had 2
keyboard replacements under warranty. The Star Labs laptop I have is [user
repairable](https://support.starlabs.systems/kb/labtop-mk-iv/star-labtop-mk-iv-complete-disassembly-guide) and
they sell spare parts for all their older range which will hopefully mean it
lasts a long time.

I’m happy with a more locked-down approach as an iPhone user because I use it
much less, and only for messaging, health/exercise tracking, and as a camera. My
laptop is my primary device so I want to have full control over it.

macOS used to offer that: a polished UI and great, native apps running within a
Unix-like OS running on the nicest hardware that allowed me to get into the
details of the command line when I was writing code.

That is still possible, but it’s eroding. Apple has always taken a more
locked-down approach, but macOS used to be much more friendly to the power user.
I now have to make a decision between having the best, cutting-edge hardware vs
the freedom and control to do what I want with the device I spend most of my
time on.

Desktop Linux is not ready for the mainstream user, although projects
like [Elementary](https://elementary.io/) are getting there. But it is ready for
anyone technical who is willing to invest the time. The philosophical reasons
are compelling: open source, control, customisation. Anecdotally I’ve seen many
developers make similar arguments. Developers are early adopters and whilst
Apple continues to make record revenues, perhaps this dissatisfaction with the
platform is a leading indicator.

There are occasional issues with Linux sound output, it requires quite a lot of
time to set everything up just right, and configuring some things needs a web
search to find someone else who has got it working. But now [my
computer](https://davidmytton.blog/iuse/) is actually mine.

I still follow Apple’s announcements and am impressed with the technology going
into the new Silicon. I’m occasionally temped back, but then I’m reminded that
Apple [doesn’t care about
developers](https://daringfireball.net/2021/02/apple_silicon_dtk_saga) and
is [behaving more and more like a
monopolist](https://stratechery.com/2020/the-antitrust-hearing-the-role-of-congress-ceo-questions/).
Their shift to services revenue is a change of incentive away from building good
software which is [already showing up in a degraded
UX](https://twitter.com/austinnotduncan/status/1243343916398592000).

It’s sad that the best of both worlds is no longer available.
