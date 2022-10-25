---
title: "The golden age of SaaS"
date: 2016-09-06
modified: 2016-09-06
draft: false
tags: ["Cloud", "Startups"]
url: the-golden-age-of-saas
---

There’s no longer any good reason to run your own software. Everything you need
to run your business is available as a service.

Even core software components like databases and queues are now available
through IaaS like Amazon’s RDS and [Google’s
pub/sub](https://medium.com/@davidmytton/how-much-is-spotify-paying-google-cloud-ebb3bf180f15).

When you buy something as a service, it will be more regularly updated and [more
secure than anything you can build or run
yourself](https://medium.com/@davidmytton/3-hybrid-cloud-myths-98b7be239070).
There only remains FUD from legacy vendors, luddites and regulatory bodies
preventing some use cases from going to SaaS. The latter will eventually change.

But that wasn’t always the case…

## 7 years ago…

In 2009 I started [Server Density](https://www.serverdensity.com/), a monitoring
as a service product. It came out of my frustrations around trying to find an
easy way to get graphs and alerts without having to do everything myself.

These were the early days of SaaS and most of the things I needed to start a
company, I had to build myself. It’s interesting to look back and what I built
and the wealth of services available now.

- **Payment processing**. The US lead the market but over here in the UK, [I
  had to go to a bank to get a merchant account and then to a payment
  processor](https://blog.serverdensity.com/taking-payments-online-merchant-account-payment-processor-fees/) to
  get an API to hook it up to. Nowadays, I can just go with Stripe or
  Braintree.
- **Hosting**. I started off at Slicehost, then upgraded to dedicated servers
  at Rackspace, which required annual commitments and pricing negotiations.
  Today I’d just go with AWS or Google Cloud, and I might even prototype the
  MVP on App Engine or AWS Lambda and simply skip the servers.
- **Accounting**. This was one of the few areas I didn’t have much pain with
  because Xero was available. It is still an amazing product and handles all
  our accounting, invoicing, expenses, balance sheet, tax, currency reporting
  needs.
- **Customer management**. Connecting Xero and our payment processing for
  subscriptions was not easy. I had to build a custom system to tie them
  together but today I would probably use Zuora.
- **SaaS metrics**. There was no established standard around reporting for
  SaaS, it was too new a business model. I reported to our investors our
  revenue each month but things like churn, LTV, CAC, ARPA, etc were very
  unusual and difficult to calculate. Today I’d use Chartmogul or Baremetrics.
  The community around SaaS has also grown significantly, with [helpful
  posts](http://christophjanz.blogspot.com/2013/12/a-kpi-dashboard-for-early-stage-saas.html) from [Christoph
  Janz](https://medium.com/@chrija) (one of my
  investors), [A16Z](http://a16z.com/2015/08/21/16-metrics/) and of course
  everything from [Jason M.
  Lemkin](https://medium.com/@jasonlk) at [SaaStr](https://www.saastr.com/).
- **Customer Succes**s. This wasn’t even a thing and discussion was around
  “customer support”. Zendesk was very early and I built a custom system to
  handle tasks, remembering to check in with customers and get basic usage
  metrics. Today I would use Totango, Gainsight or Amity.
- **Team communication**. Skype was the main tool for talking within our team.
  We then switched to Hipchat and more recently have moved to Slack. Just
  think of all the data and integrations Slack gives you right in a single
  app. That was all hidden across multiple systems in the past.
- **Code builds**. Running a buildbot server was a pain but now we simply
  connect Github to TravisCI and it all happens with minimal hassle.
- **Push notifications**. [A tutorial I
  wrote](https://blog.serverdensity.com/how-to-build-an-apple-push-notification-provider-server-tutorial/) for
  creating your own push notification server is still one of the most popular
  posts on our [devops blog](https://blog.serverdensity.com/)but nowadays you
  can use services like Urban Airship or AWS SNS.
- **Office & Storage**. Dropbox has been around since 2007 but it wasn’t so
  good for business use in the early days. It’s only recently that Google Apps
  is a full suite of email, calendar, conference calls (Hangouts, launched 2013) and storage (Google Drive, launched 2012). Microsoft have upped their
  game recently and now Office365 is actually very good. AWS have an email and
  file sharing product and there are other places to run your mail like
  Fastmail. There is absolutely no excuse for running your own email as a
  business these days. I’ve not had to deal with spam since I started using
  GMail.
- **Security**. DDoS protection and firewall services like Cloudflare, and
  even VPN like Cloak are relatively new. The old way of doing this involved a
  lot of hardware, appliances, expensive bandwidth and trying to configure
  something like OpenVPN on a server you then had to secure yourself.
- **CRM**. Of course SalesForce created SaaS but there are no end of
  alternatives that are much more lightweight and better designed. I’m on the
  board of one, [SalesSeek](https://www.salesseek.net/).

## Running a business from anywhere

SaaS means there is no single point of failure. Server Density is a distributed
team accessing various SaaS products to run our business. Failure of one does
not stop business.

Being productive just requires a) a computer, b) the internet, c) your access
credentials.

From any major city and even smaller towns around the world, you can buy a
ready-to-go laptop from Apple, log in and have your 1Password database sync
within seconds. Launch a browser and you’re ready to go. It’s [even easier on an
iPad](https://medium.com/@davidmytton/a-week-with-the-ipad-pro-as-a-startup-ceo-aa783bfb7aaa) and
outside the Apple ecosystem, similar tools exist as well.

## Starting a business is just as easy

With all these services, you no longer have to build your own business
infrastructure. You can focus purely on what your product is, with all the tools
you need to sell it, provided by expert SaaS vendors, on a monthly fee basis.

That’s not to say that creating a successful business is any easier, but
starting and running the back office certainly is.

Modern businesses shouldn’t ever have to run software themselves, except for
what they write as part of their product and even then they don’t need to create
that infrastructure from scratch. And older businesses who know what they’re
doing are moving in the same direction, it’s just the luddites left with their
on-premise data centres, appliances, servers…

Today is the golden age of SaaS.
