---
title: "Cloud emissions transparency stage 1 completed – what next?"
date: 2022-03-03
modified: 2022-03-03
draft: false
tags: ["Cloud", "IT Energy", "Carbon Awareness", "Transparency"]
summary: "Customers should now be asking their suppliers for the carbon 
footprint of the software services they buy."
url: cloud-emissions-transparency-stage-1-completed-what-next
---

Transparency is the key to sustainable computing because as more services are
outsourced to cloud and SaaS products, [customers lose the ability to report on
the impact of the resources used](https://doi.org/10.1038/s41558-020-0837-6). If
you rack a server in a data center, you can use the electricity bill to
calculate a carbon footprint. But if that is run by a cloud provider, your usage
gets wrapped up in their overall energy figures.

On 1 Mar, [AWS released its customer carbon footprint
tool](https://aws.amazon.com/blogs/aws/new-customer-carbon-footprint-tool/).
This allows all AWS cloud customers to see a breakdown of the carbon emissions
associated with their cloud resource usage by geography and service.

[I was quoted in the
WSJ](https://www.wsj.com/articles/amazon-web-services-to-share-emissions-data-as-tech-giants-race-to-green-the-cloud-11646123400) commenting
on this announcement, which is a great step for users of the big three cloud
providers – both Google and Microsoft already have similar tools available
(although Microsoft’s is only available if you have an Enterprise Azure
contract).

How these figures are calculated is a separate
question. [Google](https://cloud.google.com/carbon-footprint/docs/methodology) and [Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=56950) provide
details about their methodology, but AWS does not. [AWS also uses market-based
GHG Protocol
calculations](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/ccft-estimation.html) whereas
Google uses location-based reporting. Location-based is more useful because [it
considers where the electricity is
consumed](https://ghgprotocol.org/blog/top-ten-questions-about-scope-2-guidance) in
relation to carbon mitigation in that region e.g. renewables on the same grid as
the data center. It’s generally accepted practice to report both, but
location-based reporting is important for encouraging demand for more clean
energy where it is actually consumed.

Interestingly, AWS provides a “path to 100% renewable energy” projection as they
work towards matching their energy consumption with renewables by 2025. Contrast
this with Google which has
“[used](https://davidmytton.blog/how-can-data-centers-use-100-renewable-electricity/)”
100% renewable energy [since
2017](https://cloud.google.com/blog/topics/sustainability/google-achieves-four-consecutive-years-of-100-percent-renewable-energy).
Using Google Cloud has a net zero impact due to this matching and their offset
program which has been in place since 2007.

![Screenshot of the AWS carbon footprint tool](aws-carbon-footprint-tool.png "AWS Customer Carbon Footprint Tool, [from AWS’s
Blog](https://aws.amazon.com/blogs/aws/new-customer-carbon-footprint-tool/).")

## What do we do with the data?

Understanding the full supply chain is important to be able to calculate true
impact of the products and services an organization provides. However, scope 3
emissions reporting – everything that isn’t directly generated energy (scope 1)
or electricity purchases (scope 2) – is the big gap in how organizations report
their emissions today. This is especially true in IT and software where there is
rarely direct power generation and all the energy-intensive IT equipment is run
in the cloud.

The core cloud primitives – compute, networking, storage – form the building
blocks of most modern software. Now we can calculate the carbon footprint of
those components in any of the big three clouds, the data can be used to
calculate the footprint of the services built on top of them. For example, any
SaaS business using AWS can now calculate the carbon impact of its operations.

The benefits of the cloud – efficiency from massive scale – also apply to the
environmental footprint. Cloud customers benefit automatically from the
investments in software and infrastructure efficiency as well as the efforts
going how hyperscale operators purchase energy for their data centers.

I call this stage 1 because we now have carbon data for the lowest layer of
infrastructure. The next stage is for those relying on that infrastructure to
calculate their own footprint. Once users of SaaS and other platforms built on
the cloud can calculate their own footprint, they can report that to their
customers thereby giving them visibility into the emissions of the various tools
they use. This works its way up through the infrastructure and software stack,
creating a better picture of the full (IT) supply chain for a particular
organization.

Customers should now be asking their suppliers for the carbon footprint of the
software services they buy.
