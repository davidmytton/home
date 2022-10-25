---
title: "Obsolescence forced by software"
date: 2019-12-29
modified: 2019-12-29
draft: false
tags: ["Programming"]
summary: "Perfectly functional hardware, forced into obsolescence by software. 
Do you always want to use the latest and greatest? What about your users? How 
long should you maintain software and APIs for?"
url: obsolescence-forced-by-software
---

“I can’t check-out – it just says there is an error”, I was told by one of my
older relatives. “I put everything into my shopping cart but I have to phone
them to make the order”, she continued. “They keep telling me to clear my
cookies. What are cookies?”

5 years ago I purchased an iPad Air for my grandmother so she could order her
grocery shopping online. Her health meant she could no longer drive to the shops
so an iPad was the perfect solution. With a simple interface, a big screen and
no chance of viruses or malware, installing
the [Morrisons](https://en.wikipedia.org/wiki/Morrisons) app to order groceries
online meant she could maintain her independence.

This worked perfectly until a few months ago. For some reason, the app was
preventing her from completing her order. A cryptic message just said “An error
has occurred, try again in a few moments”. Calling customer services allowed her
to complete the order over the phone – all the items were in the cart – but she
couldn’t do this on the iPad itself. They suggested she clear her cookies which
made me suspicious – there are no cookies in a native app.

The next time I visited, I started to investigate. I replicated the problem but
the generic error didn’t explain what the issue was. There were no updates for
the Morrisons app so I decided to delete and reinstall it. After removing the
app, I went to the App Store to find that the old app no longer existed. [A new
one was in its
place](https://apps.apple.com/gb/app/morrisons-groceries/id1448677674), but it
required iOS 11 or later. The iPad Air was on iOS 9.

The settings told me that an update was available – iOS 12 – but it could not
install it over the air. No
explanation [why](https://support.apple.com/en-us/HT201435), just that I needed
to plug the iPad into a Mac and use iTunes to update it. I didn’t have my laptop
and the iPad was my grandmother’s only computer. She didn’t need a Mac, or a
Windows PC. So we were stuck until I could visit again with a full computer.

Morrisons does have a website, although it is significantly less intuitive than
the iPad app. My grandmother could use this in the meantime, but needed help
from other relatives – the website text was too small to read and touch areas
difficult to hit, even for me! Increasing the system font size had no effect –
it clearly hard coded fixed font sizes.

Several weeks later, I was able to plug the iPad into my Macbook and upgrade it
to iOS 12. I downloaded the new Morrisons app and my grandmother was able to
place her orders again. However, this episode made me think about the
inevitability of future problems, and how the tech industry treats upgrades.

## Obsolescence forced by software

The iPad Air was released in 2013 and discontinued in 2016. Apple is unusual in
how long it supports its products, but even it has a limit. iOS 12 is the final
version of iOS to support the iPad Air. iPadOS 13 – released in September 2019 –
no longer supports it. [iOS
12.4.4](https://en.wikipedia.org/wiki/IOS_12#12.4.4) was released on Dec 10 2019
specifically for devices that are not supported by iPadOS 13.

When it was released, the iPad Air was running iOS 7, an OS from 2013. Morrisons
now requires iOS 11, released in 2017. The old app had worked from at least 2013
all the way to 2019 – 6 years. That’s a long time in technology.

Yet, the iPad Air is still working perfectly. Unless it is physically broken,
there’s no reason to think it won’t continue working for many years to come.
There are no moving parts and it is not in a hostile environment. My bet is that
it will be discontinuing software support that will force an upgrade, not any
kind of hardware problem.

Perfectly functional hardware, forced into obsolescence by software.

## How long do you maintain backward compatibility?

I understand the developer perspective. I love playing with new technology, new
software and new APIs. 6 years is long time to need to maintain compatibility:
new and deprecated APIs, introducing new functionality, retiring old features,
performance and efficiency, testing on a range of old devices.

But understanding your audience is just as important.

The next major version of the open source RSS reader application
NetNewsWire [will require the latest macOS
10.15](https://inessential.com/2019/12/26/netnewswire_2020_roadmap_schmoadmap) and
the newly-beta [iOS version requires iOS
13](https://ranchero.com/netnewswire/test-ios). The users of an RSS app are
likely to be techies and the app authors want to use all the latest
functionality of those platforms, writing elegant and maintainable code. This is
a reasonable position.

In contrast, aside from some devout, hardcore iPad-only techies, the iPad is a
very mainstream consumer device. Ordering groceries from Morrisons is an equally
mainstream activity. [Analysis
suggests](http://www.asymco.com/2018/03/01/determining-the-average-apple-device-lifespan/) that
iPhones and iPads stick around for 4+ years – 2 out of 3 iOS devices ever sold
are still in use.

If you are building apps for techies then forcing users onto the latest (or
latest minus 1) platform might be a reasonable decision. If you are building
apps for mainstream users then you have to make a different calculation.

Retiring apps makes sense – I understand why Morrisons would want all new users
to migrate to their new app. But do they not have statistics showing customers
still using their older app? Everything continued working, except checkout. Was
there no way to maintain backward compatibility? Windows APIs have significant
backward compatibility, with some effort, [all the way back to Windows
3.1](http://yeokhengmeng.com/2019/12/building-a-new-win-3-1-app-in-2019-part-1-slack-client/).

I expect Morrisons changed their checkout or payments API behind the scenes –
perhaps they knew they had few users on the old app and decided they would just
force it. But then I wonder why they didn’t set up a better error message.
Customer service clearly had no clue because asking the user to clear cookies
with a native app makes no sense. What would my grandmother have done without me
investigating, or if I had no laptop? Either buy a new iPad or continue using
the website.

This is [not a deliberate conspiracy to force users to
upgrade](https://daringfireball.net/2017/12/iphone_battery_throttling) but it’s
also [not great for the idea of the circular
economy](https://davidmytton.blog/environmental-circular-economy-and-resource-efficiency-pledges-in-the-uk-general-election-2019/).

## Lessons for app developers

- Clearly define your intended audience and understand what constraints that
  places on your development practices. Your approach will be different
  depending on where your users fall on the [diffusion of innovations
  scale](https://en.wikipedia.org/wiki/Diffusion_of_innovations).
- If unsure, follow the example of the major tech platforms for their own
  products. The iPad Air is unusual in how long it has been supported by iOS,
  only going end of life at the end of 2019. If Apple are continuing to
  support it 3 years after it was discontinued (and you have produced an app
  for that platform) then you should support it just as long.
- Review your statistics. Apple provides developers with an App Store Connect
  dashboard of [stats showing which platforms users are
  on](https://help.apple.com/app-store-connect/#/itc14b94d665) so you don’t
  need to install privacy invading trackers. Other platforms probably do the
  same.
- [Version your
  APIs](https://www.troyhunt.com/your-api-versioning-is-wrong-which-is/) and
  provide backward compatibility when you introduce new versions. Determine
  how long you will keep APIs alive before sunsetting based on your audience
  profile and usage stats.
- If you do break backward compatibility, provide useful error messages and
  train your customer support team to offer useful advice. Consider
  the [Microsoft](https://docs.microsoft.com/en-gb/windows/win32/uxguide/mess-error) and [Apple](https://developer.apple.com/design/human-interface-guidelines/macos/windows-and-views/alerts/) design
  guidelines for errors.
