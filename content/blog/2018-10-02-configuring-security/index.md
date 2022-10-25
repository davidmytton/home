---
title: "Configuring for security, privacy and convenience"
date: 2018-10-02
modified: 2018-10-02
draft: false
tags: ["Security", "Privacy"]
url: configuring-for-security-privacy-and-convenience
---

Balancing security, privacy and convenience is not easy. I’ve spent quite a lot
of time figuring out how to configure my various computer systems with this goal
in mind.

Computers are supposed to make our lives more convenient and you sometimes have
to trade privacy for convenience e.g. Outlook processing emails to allow you to
use Focused Inbox. AI is going to bring a lot of productivity improvements but I
always prefer when that is processed on device, as with Siri Suggestions for
things like when to leave for an event.

You also have to consider your adversary.  There are reasonable steps you can
take without seriously damaging convenience to provide safeguards against
criminals and data profiling. But if you are trying to evade active government
surveillance rather than just avoid being swept up in mass snooping, then things
get significantly more difficult.

Targeted surveillance is, and should be, allowed (with appropriate legal
safeguards). That is not what I’m trying to protect against here. Good security
should be expected by all. Privacy is about having choice and control over your
personal data.

Here’s how I approach it as of Oct 2018. I expect these practices to change over
time. In no particular order:

- Only use Apple mobile devices. They are the only company that builds privacy
  by design into their products. Their business model is to sell high priced
  hardware, not to sell your data. They have 5 year lifecycles on software
  updates which are delivered regularly, unlike Android which requires updates
  to go through carriers (usually delays by months, or forever). Buying direct
  from Google means giving up all your privacy. And the Apple model is to run
  as much computation on-device, whereas Google is the opposite – all
  processing is in their cloud environment, which is secure, but has no
  privacy.
- Don’t get an Alexa device or Google Home. If you want a voice assistant,
  Apple’s HomePod with [iOS 12
  Shortcuts](https://support.apple.com/en-gb/guide/shortcuts/welcome/ios) works
  very well.
- [iOS is the only secure OS that achieves the security, privacy and
  convenience
  balance](https://techsolidarity.org/resources/basic_security.htm). Any
  sensitive work should be restricted to iOS devices only. macOS is the next
  best option. If you don’t need convenience,
  use [Tails](https://tails.boum.org/).
- Configure [macOS](https://spreadprivacy.com/mac-privacy-tips/) and [iOS](https://spreadprivacy.com/iphone-privacy-tips/) for
  privacy. In particular, this means using full disk encryption and strong
  passwords.
- Don’t use any Google services and be sure to pay for key services like
  email, calendar and file storage. If you’re not paying then your data is the
  product – you want a vendor who has a sustainable business model in selling
  the service/product itself, not your data. Running your own systems
  significantly reduces the security aspect of the balance, so it’s better to
  use either iCloud (if you don’t want your own domain), [Microsoft
  Office365](https://www.office365.com/) (which is what I use)
  or [Fastmail](https://www.fastmail.com/). For £10/m I get access to 1TB of
  OneDrive storage, Mail, Calendar and the full suite of Office products. I
  pay an extra £1.50/m on top of that for [Advanced Threat
  Protection](https://products.office.com/en-us/exchange/online-email-threat-protection).
  Microsoft allows you to select the country where data is stored,
  has [privacy by
  design](https://products.office.com/en-ca/business/office-365-trust-center-privacy) and [has
  a good
  record](https://en.wikipedia.org/wiki/Microsoft_Corp._v._United_States) of
  defending against government access requests. The Outlook iOS app is
  actually very good but the Exchange protocol is supported by every client,
  so you have a good choice. [Focused
  Inbox](https://support.office.com/en-us/article/Focused-Inbox-for-Outlook-f445ad7f-02f4-4294-a82e-71d8964e3978) is
  great. Bigger corporates like Microsoft have significantly more resources to
  invest in security (which is why I prefer Office365 over Fastmail).
- Unfortunately, Apple Maps is still rubbish compared to Google Maps. They’re
  generally comparable in major cities so I always prefer Apple Maps until the
  last-mile destination directions, where Apple Maps is regularly inaccurate.
  At that point I switch to Google Maps on iOS.
- Don’t store anything unencrypted on cloud storage providers that you would
  be concerned about leaking if someone gained access. Encrypt these files
  individually. You can use [gpg](https://gpgtools.org/) on Mac but it’s not
  especially user friendly. I prefer [Keybase](https://keybase.io/) but it
  still requires using the command line. These files will be inaccessible on
  mobile so you may want to consider using 1Password document storage instead,
  for small files (they have a total storage limit of 1GB). Office files can
  be password protected themselves, [which uses local AES
  encryption](https://en.wikipedia.org/wiki/Microsoft_Office_password_protection).
- Delete files you don’t need any more and aren’t required to keep for tax
  records. In particular, set your email to delete all messages after a period
  – the shorter the better. [I delete all my emails after 1
  year](https://davidmytton.blog/email-is-not-a-good-database/). Configure
  macOS Finder Preferences to remove items from the Trash automatically after
  30 days.
- Don’t send attachments via email. You might delete your emails after a time
  but the recipients probably don’t. Instead, share them using an expiring
  link to online cloud storage.
- Use a password manager and 2 factor authentication. [These are just security
  basics](https://davidmytton.blog/cyber-security-leaving-the-door-unlocked/).
- Don’t use Google Chrome. Only use Safari or Firefox. Configure your browser
  to auto clear your history on a retention period that allows convenience but
  also privacy. I set mine to clear after 1 week. I’ve never needed to go back
  any further. Be sure the “Prevent cross-site tracking” option is configured
  in Safari settings.
- Set up [DuckDuckGo](https://duckduckgo.com/) for your search provider on
  macOS and iOS. I’ve not used Google search for years.
- Buy [1Blocker X for iOS and 1Blocker](https://1blocker.com/) for macOS ([see
  a comparison of other
  options](https://brooksreview.net/2018/09/safari-content-blocker-evaluations-92618-edition/))
  to block trackers and ads in Safari.
- Set up [Little Snitch outbound
  firewall](https://www.obdev.at/products/littlesnitch/index.html) and be sure
  you know which apps you’re approaching outbound internet access for.
- Set up [Micro
  Snitch](https://www.obdev.at/products/microsnitch/index.html) to be notified
  whenever your mic and camera are in use. Cover your device cameras as a
  backup.
- Don’t use SMS – disable fallback in iOS settings. WhatsApp encryption is
  good but all the metadata about who you are communicating with is shared
  with Facebook. Unfortunately, it has built up a considerable network effect
  so it is necessary to use it to communicate in the Western world. Few people
  use Signal, which is the best so  [follow this guide to maximise WhatsApp
  privacy](https://medium.com/@mshelton/upgrading-whatsapp-security-386c8ce496d3).
  iOS allows you to configure deleting iMessages after a period of time. I
  have mine set to delete after 30 days. You have to manually clear your
  WhatsApp conversations.
- Don’t plug anything directly into any USB charging port in airports, hotels,
  or anywhere else. [Use a USB data blocker adapter
  first](https://www.amazon.co.uk/PortaPow-3rd-Data-Blocker-Pack/dp/B00T0DW3F8).
- Back up your files to cloud storage but only if they are encrypted locally
  first. [Arq](https://www.arqbackup.com/) is a good tool to do this. Don’t
  use the same cloud storage as your main files e.g. I use OneDrive for my
  files and Amazon S3 for Arq backups.
- Always use a VPN when connected to public wifi, or any network you don’t
  control, but don’t use a free VPN. [This site has a good
  comparison](https://thatoneprivacysite.net/vpn-comparison-chart/) but I
  use [Encrypt.me](https://encrypt.me/) on macOS and iOS. Encrypt.me is owned
  by [StackPath](https://www.stackpath.com/), [my current
  employer](https://www.stackpath.com/media-and-analysts/press-releases/2018/stackpath-and-server-density-merge/),
  so I know how all the internal infrastructure is set up i.e. [we don’t log
  traffic](https://encrypt.me/policies/#our-data-collection-retention-policy).
  However, I also used it prior to joining StackPath and [before Encrypt.me
  itself was
  acquired](https://blog.encrypt.me/2016/04/28/cloak-joins-stackpath/).
  Encrypt.me is a great consumer VPN but if you want more control and
  configuration options e.g. OpenVPN
  support, [StrongVPN](https://strongvpn.com/) is another product from
  StackPath.
- Change your DNS servers to use a privacy-first DNS provider, [such as
  Cloudflare DNS](https://1.1.1.1/). Do not use your default ISP DNS or Google
  DNS. If you have an OpenWRT router, [configure it to use Cloudflare DNS over
  TLS](https://blog.cloudflare.com/dns-over-tls-for-openwrt/) because
  otherwise your ISP can still sniff your DNS requests.
- Better yet, buy a router that allows you to configure DNS over TLS and
  connect to a VPN directly. I have
  a [GL-AR750S](https://www.gl-inet.com/products/gl-ar750s/) configured to
  force all DNS over Cloudflare DNS over TLS and it is permanently connected
  to StrongVPN. This means all connections from home are encrypted before they
  even hit my ISP. The only downside is having to disconnect the VPN when
  using BBC iPlayer, because it detects the VPN. My wifi uses Mac whitelisting
  so only specific devices are allowed to connect.
- [Pay for Cifas protective
  registration](https://www.cifas.org.uk/services/identity-protection/protective-registration) and
  register your phone numbers on the [TPS
  list](https://www.tpsonline.org.uk//tps/index.html).
- Use Apple Pay wherever possible. The vendor doesn’t get access to any
  information about you and can only identify your payment information [from a
  token specific to each transaction](https://kirklennon.com/a/applepay.html).
  This protects privacy and if the vendor is breached, your card details are
  safe. The usual contactless limit doesn’t apply to Apple Pay, which is
  limited only by your card limit.
- [Don’t buy Samsung TVs](https://www.bbc.co.uk/news/technology-31296188).
  There’s no need for any TV to connect to the internet so don’t connect them
  in the first place. Use a dedicated device like an Apple TV for your TV
  interface, it has a better UI anyway.
- Be mindful of sharing photos online directly from your phone. They usually
  embed the location of the photo in the EXIF data.

Have I missed something? [Let me know](mailto:david@davidmytton.co.uk) what else
you’re doing.
