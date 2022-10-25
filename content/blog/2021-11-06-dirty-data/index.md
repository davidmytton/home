---
title: "Dirty data? Carbon footprint of photo storage"
date: 2021-11-06
modified: 2021-11-09
draft: false
tags: ["Data Center Energy", "IT Energy", "Transparency"]
summary: "An example of poor quality research with flawed assumptions designed 
as click-bait to get news coverage timed to land during COP26. Deleting a few 
photos will have zero impact on your carbon footprint."
url: dirty-data-carbon-footprint-of-photo-storage
---

Last week I appeared on Kay Burley’s Breakfast Show on Sky News to discuss new
stats about the carbon footprint of “unwanted” photos.

According to [the press release from The Institution of Engineering and
Technology](https://www.theiet.org/media/press-releases/press-releases-2021/26-october-2021-dirty-data/) (IET):

> New research today reveals Brits’ hidden dirty data habits, with the nation’s
> trigger-happy social snappers contributing over 355,000 tonnes of CO2 every
> year through unwanted pics alone: the equivalent to the entire population of
> Chelmsford flying to Australia and back. The new study by the Institution of
> Engineering and Technology (IET), found just a quarter of respondents delete
> additional shots they take, leaving millions of identical images being added
> to storage every week. And for those that do delete their excess pictures,
> fewer than one in six (16%) say they do this for environmental reasons (i.e.,
> to reduce the burden of energy needed to power servers used to store our data
> dumps). With the average person taking almost 900 photos per year the
> duplicated, unwanted images left in storage alone could accumulate 10.6kg of
> CO2 emissions annually for every adult in the UK – the equivalent of over
> 112,500 return flights from London to Perth, Australia.

As I said on-air, there are problems with these figures. In this post I’ll
discuss why I think they’re bogus.

![Image of David Mytton on Sky News](sky-news.jpg "Me on Sky News!")

## Photos on the phone

Thanks to regulation
([US](https://en.wikipedia.org/wiki/Energy_Star) and [EU](https://ec.europa.eu/energy/topics/energy-efficiency/targets-directive-and-rules/energy-efficiency-directive_en)),
electrical devices have become more and more efficient over the last few
decades. This means the majority of the carbon footprint of the phone is in the
manufacturing stage. For example, [the latest Apple iPhone 13 is responsible for
64 kg of lifecycle carbon
emissions](https://www.apple.com/euro/environment/pdf/a/generic/products/iphone/iPhone_13_PER_Sept2021.pdf),
only 16% of which is its usage (over an assumed 3 year lifespan).

Phones have an internal battery which is charged periodically, generally
overnight. Battery drain depends on the usage pattern, and mobile operating
systems have been getting more sophisticated power management over the years.

The file format also has an impact. In 2017, Apple introduced a new file format
– [HEIF](https://en.wikipedia.org/wiki/High_Efficiency_Image_File_Format) –
which uses up to half the storage size as an equivalent JPEG. Other operating
systems followed. Is this factored into the calculations?

Calculating how much energy is consumed by taking a single photo is difficult.
You’d need to measure the tiny amount of power consumption before and after
taking a photo. Accurately inspecting that energy consumption is challenging
because of factors like other operating system tasks, the charge state of the
battery, and the ability to measure such a small unit of work. Taking a photo
takes less than a second. Compare that to 1 hour of video streaming, which gives
a much larger period to measure over.

Taking the photo is just one component. Storage is another. All phones use solid
state disks which have a set power consumption during read/write, but have a
very low profile when idle.

Then you’d need to multiply by the carbon factor for the power grid where the
phone was charged.

Phones are charged by electricity, which has a carbon intensity factor that will
depend on the grid mix when it was charged. As this “study” was focused on the
UK, we can say that over the past 10 years the UK grid mix has shifted
significantly towards renewable electricity. There is a lot more progress
needed, especially internationally, but the electricity grid is rapidly
decarbonising.

The study doesn’t provide any reference year, so are they refering to the carbon
emissions in 2009…or 2018? The carbon factor for the electricity used to charge
the phone would be very different in each case.

Either way, the grid emissions are not something a phone user has much control
over, and will change every time the phone is charged.

![Graph of UK annual electricity generation](annual-uk-electricity.png "Annual
electricity generation in the UK by type of fuel (terawatt hours).
Source: [BEIS](https://www.gov.uk/government/statistical-data-sets/historical-electricity-data), [BM
Reports](https://www.bmreports.com/bmrs/?q=eds/main), [Sheffield
Solar](http://www.solar.sheffield.ac.uk/pvlive/) and Carbon Brief
analysis. [Chart by Carbon
Brief](https://www.carbonbrief.org/analysis-uk-electricity-generation-2018-falls-to-lowest-since-1994).")

## Photos in the cloud

Once taken, the photo might then be uploaded to the cloud. If you’re on an Apple
device this will probably be iCloud. On Android, it’ll probably be Google
Photos. It may also be shared on Facebook (via Instagram, WhatsApp or Facebook
itself). Depending on the settings, the photo may then be automatically deleted
from the device (usually to save space).

When the photos are uploaded also has an impact. The default settings usually
mean photos will only be uploaded when the phone is on wifi (which is less
energy intensive than cellular) and when it has sufficient battery charge.

In the case of iCloud, Apple has been running it’s data centres on 100%
renewable electricity [since
2013](https://www.datacenterdynamics.com/en/news/apple-reaches-100-renewable-energy-across-all-data-centers/) (and [all
its global facilities since
2018](https://www.apple.com/newsroom/2018/04/apple-now-globally-powered-by-100-percent-renewable-energy/)).
Google has been doing this [since
2017](https://sustainability.google/progress/projects/announcement-100/).
Facebook is not quite as good, but achieved this [as of
2020](https://sustainability.fb.com/report-page/energy/). Although [that doesn’t
actually
mean](https://davidmytton.blog/how-can-data-centers-use-100-renewable-electricity/) the
electricity going into the data centre has been generated from 100% renewable
sources 24/7, the combination of renewables matching with offsets means that on
a reporting basis there is zero carbon associated with storing these photos in
the cloud.

We also don’t know the architecture of the systems behind these cloud services.
If you have ever used a cloud storage product like AWS S3 or Google Cloud
Storage, you’ll be aware of the different storage tiers you can set up depending
on how frequently you access the data. Photos just uploaded may be stored in hot
storage so they can be viewed/shared immediately, but over time they may be
moved into cold storage for infrequent access.

For example, Facebook has written about this in the past:

> As the number of photos continued to grow each month, we saw an opportunity to
> achieve significant efficiencies in how we store and serve this content and
> decided to run with it. The goal was to make sure your #tbt photos from years
> past were just as accessible as the latest popular cat meme but took up less
> storage space and used less power. The older, and thus less popular, photos
> could be stored with a lower replication factor but only if we were able to
> keep an additional, highly durable copy somewhere else.
>
> [Under the hood: Facebook’s cold storage
> system](https://engineering.fb.com/2015/05/04/core-data/under-the-hood-facebook-s-cold-storage-system/)

The network carbon intensity is not factored into this – and individual ISPs
still have a lot of work to do compared to the big cloud providers – but placing
photos in the cloud is the most sustainable location for them.

## Where are the emissions?

The number cited by IET is 10.6kg of annual CO2 emissions. This is not from the
900 photos that each adult supposedly takes each year, but an “unwanted” subset
of that total.

This is based on an original survey carried out by the IET which says that 25%
of respondents delete additional shots they take, and 69% do not delete
duplicated photos.

What does “unwanted” or “additional” mean? It’s not defined.

So if we assume that `25% of 900 = 225` “unwanted” photos, the IET are saying
that 225 photos are responsible for 10.6kg of emissions per year. `10.6 / 225 = 0.047 kg` per photo, or 42.4kg for 900 photos.

How realistic is this? We can check it against the lifecycle emissions of an
iPhone 13 = 16% of 64kg = 10.24kg. But that’s over a 3 year lifecycle. That
means 3.41kg per year of full use.

These numbers don’t make sense – the IET number is x12 larger! Apple reports
that using the phone for a full year will cause 3.41 kg of carbon emissions. The
IET says that taking 900 photos per year will cause 42.4kg of carbon emissions.

If there are zero emissions associated with cloud storage, where does that
figure come from? It’s clearly bogus.

## Poor quality research

This release by the IET is an example of poor quality research with flawed
assumptions designed as click-bait to get news coverage timed to land during
COP26. It has multiple problems:

- There are no workings. The sources for the numbers are not provided, and the
  references do not back up the claims.
- Simplistic calculations. There is no understanding of the lifecycle emissions
  of the phone, the varying grid mix is not accounted for, where the photos are
  stored is not considered, the emissions profile of the cloud is ignored, the
  storage architecture of the cloud is not discussed.
- There is no sense-checking against readily available figures. A figure that is
  x12 higher than the lifecycle analysis published by the manufacturer doesn’t
  make sense.
- The conclusions are based on a survey of user behaviour that uses vague terms
  to model “bad” behaviour. Who decides what is “unwanted”? That will be
  different for every person.
- It ignores the published research showing that [energy consumption has
  decoupled from demand](https://doi.org/10.1088/1748-9326/aaec9c).
- These conclusions are used to recommend that deleting a few photos or clearing
  your WhatsApp chats will have a meaningful impact on the environment. This
  makes people feel good without having any actual impact.

The way to make meaningful change is to pressure organisations to decarbonise
their supply chains and infrastructure. When Google switches its data centres to
renewable electricity, users get that benefit by default. When Apple improves
the environmental status of its supply chain, users get that benefit by default.

Trying to convince individuals to change their behaviour is the wrong place to
focus. A few people might adjust their habits, but the global impact rounds to
zero. It’s significantly easier to decarbonise electrons than atoms. If you want
to have an actual impact on your carbon footprint, [not buying a new phone or
laptop is the best way to do
so.](https://davidmytton.blog/the-environmental-impact-of-buying-a-new-laptop-comparing-the-macbook-air-and-surface-laptop/)

It’s disappointing that the IET decided to waste time on these absurd scare
figures when they could have had much more impact by highlighting how little we
know about most supply chains. Google and Apple are in the minority of companies
making progress. If they want to focus on tech, there’s plenty to criticise
([water consumption](https://davidmytton.blog/data-centre-water-consumption/),
for example). We know almost nothing about other industries. [That’s why
transparency is the first step to catalysing
change](https://davidmytton.blog/sustainability-doesnt-work-without-transparency/).
