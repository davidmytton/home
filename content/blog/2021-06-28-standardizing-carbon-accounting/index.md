---
title: "Standardizing carbon accounting"
date: 2021-06-28
modified: 2021-06-28
draft: false
tags: ["IT Energy", "Transparency"]
summary: "It is currently impossible to properly compare how sustainable one 
product is vs another. Pictures of wind farms look nice, but how do you choose 
which cloud region to deploy (or move) your resources if there is no way to 
compare them?"
url: standardizing-carbon-accounting
---

It is currently impossible to properly compare how “sustainable” one product is
vs another. Unlike financial accounts for investing, nutritional content in food
and even [how warm a duvet is](<https://en.wikipedia.org/wiki/Tog_(unit)>), there
is no commonly accepted method of measuring “sustainability”. This is a problem
when brands claim they are “more sustainable”. Compared to what? On what basis?

My favorite example is the move to discourage use of plastic bags by charging
for them at checkouts. This has reduced the number of plastic bags in
circulation, but if the goal has been to replace them with more environmentally
friendly options, the policy is probably a failure. If you are using an organic
cotton tote bag instead, the full lifecycle impact of that single bag bag causes
more damage to the environment (on all factors from climate change to ecosystem
decay and acidification) than 20,000 plastic bags
([source](https://www2.mst.dk/Udgiv/publications/2018/02/978-87-93614-73-4.pdf)).

The lack of standardization has been an ongoing challenge in my sustainable
computing research. Pictures of wind farms and solar panels look nice, but how
do you choose which cloud region to deploy (or move) your resources if there is
no way to compare them, ideally in near real-time?

Google has started to publish its [carbon data across Google Cloud
regions](https://cloud.google.com/sustainability/region-carbon). It reports the
grid carbon intensity as well as the carbon free energy percentage because [no
region currently operates on 100% renewable energy
24/7](https://davidmytton.blog/how-can-data-centers-use-100-renewable-electricity/).
Google offsets the net carbon emissions so using Google Cloud is always net-zero
carbon from a Scope 3 market perspective, but not on a location basis.

These figures are directionally useful. You can deploy resources to the most
carbon free energy region historically on an annual basis – but as they are
figures for 2019, you can’t use them to dynamically move resources to use the
least carbon intensive energy right now. We can use the Google Cloud carbon data
to compare between GCP regions, but what about against Azure, or AWS, or against
a colocation facility? This is not currently possible.

Markets only work where there is information symmetry amongst participants. That
information must be standardized and mandatory to disclose so that everyone
involved has the ability to compare and make informed choices depending on their
priorities. If we’re going to include sustainability as a selection criteria, we
need to develop a standardized method of calculation so decisions based on those
metrics are robust.

Work on this has started. The International Financial Reporting Standards (IFRS)
Foundation recently concluded a [consultation on sustainability
reporting](https://www.ifrs.org/projects/work-plan/sustainability-reporting/) and
the US Securities and Exchange Commission (SEC) has been [soliciting comments on
climate change
disclosures](https://www.sec.gov/news/public-statement/lee-statement-review-climate-related-disclosure).
Microsoft is one of the organizations participating and in a public submission,
they state:

> the development of universally understood and calculated measures for Scope 1,
> 2, and 3 emissions would allow investors to easily compare the performance of
> similarly situated companies. Additionally, as Microsoft and others go beyond
> carbon reduction to carbon removal, it is important to have common measures
> for negative consumption. Just as we have well-understood, precise metrics for
> currency in finance, kilowatt hours in energy, and calories in food products,
> precise measures of emissions would allow investors and other stakeholders to
> make meaningful comparisons and informed decisions.
>
> <cite>[Microsoft’s SEC submission on Climate Change Disclosures (June 14 2021)](https://blogs.microsoft.com/wp-content/uploads/prod/sites/5/2021/06/MSFT_comments_climate_change_disclosure.pdf)</cite>

If sustainability is a metric that consumers care about – [and there are major
indicators that they
do](https://www.nielsen.com/us/en/insights/article/2018/global-consumers-seek-companies-that-care-about-environmental-issues/) –
then those companies will benefit from better reporting. This will flow down the
supply chain so that everyone involved can report accurate sustainability
statistics. Currently, only a select few who have total control of their supply
chain (like Apple) can force their suppliers to do the hard work needed to
calculate metrics like carbon emissions. For everyone else, their supply chain
is opaque.

Including standardized carbon accounting metrics as a mandatory part of company
reporting is a good step towards the goal of “sustainability” as a measurable,
comparable characteristic. This is an example of where government can engage in
light touch regulation by forcing consistent standards of transparency, then
leave it to the market to decide what the information means for daily
decision-making.

We see this all the time in financial markets. Everyone understands the concept
of profit because it is calculated and reported consistently by every
organization. Some investors prefer to put their money in businesses that have
consistent profits (but probably low growth). Others prefer to invest in earlier
businesses that have no profits, but with the expectation of future growth and
profit. The government doesn’t tell you where to put your money – it ensures you
have enough information to make that choice yourself. This helps fund all sorts
of new companies, ideas and innovation.

That is the power of transparency, and we need more of it.
