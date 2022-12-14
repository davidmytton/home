---
title: "Assessing the suitability of the Greenhouse Gas Protocol for calculation of emissions from public cloud computing workloads"
date: 2020-08-08
modified: 2020-08-08
publication: Journal of Cloud Computing
showTaxonomies: true
canonicalUrl: "https://doi.org/10.1186/s13677-020-00185-8"
githubMaterials: "https://github.com/davidmytton/paper-assessing-ghg-protocol-for-public-cloud"
summary: "Efficiency improvements over the past decade have meant that data center energy usage has decoupled from the growth in IT workloads. Much of this efficiency improvement has been attributed to innovations made by “hyperscale” public cloud vendors, where a large proportion of new IT workloads are now being deployed. However, the move to the cloud is making it more difficult to assess the environmental impact of workloads deployed there. Although the large cloud vendors are amongst the largest purchasers of renewable electricity, customers do not have access to the data they need to complete emissions assessments under the Greenhouse Gas Protocol. Data such as Power Usage Effectiveness, emissions factors and equipment embodied energy are not available from public cloud vendors. This paper demonstrates how the Greenhouse Gas Protocol method of assessment of IT emissions does not work for public cloud environments and suggests how this can be tackled by the cloud vendors themselves."
draft: false
tags: ["Data Center Energy", "IT Energy", "Cloud"]
url: publications/2020-cloud-computing-assessing-ghg
fullText: true
---

{{< alert "list" >}}
**Citation:** Mytton, D. Assessing the suitability of the Greenhouse Gas Protocol for
calculation of emissions from public cloud computing workloads. J Cloud Comp 9,
45 (2020). <https://doi.org/10.1186/s13677-020-00185-8>
{{< /alert >}}

## Abstract

Efficiency improvements over the past decade have meant that data center energy
usage has decoupled from the growth in IT workloads. Much of this efficiency
improvement has been attributed to innovations made by “hyperscale” public cloud
vendors, where a large proportion of new IT workloads are now being deployed.
However, the move to the cloud is making it more difficult to assess the
environmental impact of workloads deployed there. Although the large cloud
vendors are amongst the largest purchasers of renewable electricity, customers
do not have access to the data they need to complete emissions assessments under
the Greenhouse Gas Protocol. Data such as Power Usage Effectiveness, emissions
factors and equipment embodied energy are not available from public cloud
vendors. This paper demonstrates how the Greenhouse Gas Protocol method of
assessment of IT emissions does not work for public cloud environments and
suggests how this can be tackled by the cloud vendors themselves.

## Introduction

Estimates of annual data center electricity usage vary from 200 terawatt hours
(TWh) [43] to 500 TWh [11]. The lower of these figures would suggest that data
centers consume 1% of global electricity [43], but this could be significantly
higher. One study suggests that global data center energy usage was 270 TWh in
2012 [66]. Another study estimates that 104 TWh will be used by European Union
data centers in 2020, which makes a global total of 200 TWh unlikely [9].

This uncertainty also extends to efficiency estimations. As of 2018, IT
(Information Technology) workloads have grown significantly compared to 2010 -
×6 more compute instances, ×10 more network traffic and ×25 more storage in
2018, yet it is reported that data center energy usage has only grown by 6% over
that time [49]. Some reports support this by showing that average Power Usage
Effectiveness (PUE) is improving [9], but industry survey data suggests average
PUE values have plateaued [45]. Future energy usage is uncertain: efficiency
improvements may be “frozen” [61] and some scenarios suggest data center energy
usage could double by 2030 [7].

Whether data center energy usage grows modestly or increases significantly, even
with the increasing use of renewables in the technology sector [44] data center
emissions and other associated environmental impacts still need to be accounted
for.

In the past, IT was run in-house (also known as “on-premise”). IT teams would
buy physical servers, disks and network devices from vendors such as Dell,
Seagate and Cisco, then install them into data centers. These data centers might
be built and operated by the company itself, or space would be rented
(“co-located”) in large scale facilities, such as those run by Digital Realty or
Equinix. The company would pay for the space required to deploy the number of
servers they needed, install internet access and purchase power, typically
over-provisioning their equipment to ensure they had spare capacity.

IT applications running on physical hardware have a known (or knowable)
footprint. The equipment is self-contained and can be traced to a manufacturer
so the embodied cost of components can be calculated. Data center
characteristics such as power and cooling levels can be monitored. Emissions
factors for the electricity mix can be determined. As such, it is possible to
calculate the environmental footprint of a deployment.

Guidelines exist for creating energy efficient data centers [38] and metrics
such as Power Usage Effectiveness (PUE) can be calculated [40].

PUE is a widely used metric and often cited to show progress in data center
efficiency. For example, Google publishes quarterly and trailing 12-month PUE
values going back to 2008 for their global fleet of 15 data centers [29]; the
latest Google Q1 2020 fleet wide PUE is 1.09. However, PUE has been criticised
when used as a measure of efficiency because it only considers energy. PUE can
decrease when IT load increases even though efficiency may not have improved
[16]. It has also been shown to correlate poorly with carbon emissions [47, 48]
and should not be the only metric tracked [70].

Water Usage Effectiveness as a site based metric (WUE), combined with its
complementary source based metric (WUEsource) [57], are important environmental
indicators because of the large volumes of water that data centers require,
projected to be 660 billion litres for US data centers in 2020 [60]. Most of
this water is used in electricity generation, which is why the WUEsource metric
includes external water intensity factors, not just the operational water usage
at a point in time [57]. Although moving to renewable sources of electricity
generation helps reduce WUEsource because wind and solar energy have low water
footprints [64], less than a third of data center operators track any water
metrics [36]. Facebook is one of the few companies who report both PUE and WUE
figures publicly [21]. Other metrics such as Renewable Energy Factor (REF) [41]
and Energy Reuse Factor (ERF) [39] exist as international standards but are
difficult to find in public disclosures.

Understanding when to refresh hardware is another element to consider. In a
survey of European data centers, IT equipment older than 5 years was shown to
consume 66% of energy despite only representing 7% of capacity [11]. However,
replacing equipment less than 4.5 years old may cost more in hardware than is
saved on energy efficiency [11]. This highlights the importance of lifecycle
analysis because hardware refresh rates and overall utilisation impact the
environmental footprint of a data center, potentially offering more energy
savings than decreasing PUE [10].

With the availability of cloud computing services from vendors such as Amazon
Web Services (AWS), Google Cloud Platform (GCP) and Microsoft Azure, workloads
are increasingly being deployed into public cloud services [23]. This trend is
demonstrated by the growth of the global cloud computing market over the last
decade. From just under $6bn in 2008, as of 2019 it had reached $208bn and is
projected to grow to $236bn in 2020 [23]. Server equipment purchases are growing
at 3% per year, almost entirely attributable to “hyperscale” cloud vendors [60].
Estimates suggest 40% of servers will be in hyperscale data centers in 2020
[60].

This move to the cloud has made it much more difficult to estimate associated
emissions. Public cloud vendor customers purchase virtual services so it is
difficult to know what underlying physical resources are used because they have
been abstracted by complex software or platform layers. Customers migrating to
the cloud must also ensure their cloud architecture is equivalent to their
on-premise hardware deployments in terms of availability and redundancy to
ensure that comparisons are accurate. Cloud vendor customers have no insight
into the energy usage of the services they buy, and often do not even know how
many physical servers their applications are running on. Instead, they pay for
precise usage such as CPU time, allocated memory or execution time. In theory
the price should include the full costs of components like power and disks, but
the number is not transparent. Much is hidden behind opaque cloud vendor
pricing. Some vendors have used marketing efforts to explain why public cloud is
“greener” than on-premise [1, 51] but do not provide specific, detailed numbers
behind their claims. Models such as CLEER [47, 48] can make assumptions, but
there are so many variables that their accuracy is questionable, particularly
across use cases and as the model ages.

With an increased public awareness of environmental issues [69] and more
businesses being covered by mandatory reporting [20], cloud vendor customers
should expect to be able to calculate the environmental footprint of their IT
environment just as if they were running it on-premise. This has been possible
historically: the GHG Protocol reporting guidance assumes a range of measures
such as server count, data center PUE and capacity are available [27]. However,
the current approach by public cloud computing vendors makes it difficult to
obtain that information.

Several studies [13,14,15, 17, 24, 25] have proposed new approaches where
workloads can be dynamically moved based on various “follow-the-renewables”
criteria [15] about the underlying data center e.g. regional wind power
availability. These techniques can work well if the system has access to data to
make the right decisions e.g. emissions factors related to the data center
energy input, external temperatures related to cooling requirements, wind speeds
in the relevant geographies for each data center, etc. If the customer is
running their own data center or is deployed in a co-location facility, then
they should be able to get access to this information. However, this is not
possible with public cloud. As this paper will discuss, the major cloud
providers do not release most of these underlying data, and if they report
anything it is usually only in aggregate, not real-time.

This paper develops a framework for understanding the boundaries of a public
cloud computing environment, then uses that framework to evaluate whether the
Greenhouse Gas (GHG) Protocol is suitable for calculating emissions from cloud
workloads. It also considers what cloud vendors have done and should do in the
future to allow customers of public cloud to calculate their own environmental
footprint.

## Defining cloud vendor components

A Cloud Vendor is a commercial organisation that builds and operates the cloud
services. These are sold to the public whereby anyone can sign up with a credit
card to become a customer, usually on a pay-as-you-go basis. The components
which make up the Cloud Vendor are public in the sense that anyone can pay to
use them, and the resources are shared amongst all customers. This is also known
as “multi-tenant”. Some Cloud Vendors offer services only available to specific
sectors e.g. AWS GovCloud for the United States Government, and some products
from Cloud Vendors are run in private data centers e.g. Azure Stack, but for the
purposes of this paper, a Cloud Vendor is one which primarily sells on a public
model. Private clouds run by organisations on their own on-premise equipment are
excluded from this definition.

The core cloud services are the three Primitives: Compute, Storage and
Networking.

1. **Compute** is most commonly in the form of Virtual Machines (VMs) sized
   based on the desired quantity of memory (RAM) and processor (CPU) cores, then
   billed based on the number of seconds or minutes the VM is running. VMs are
   known as “multi-tenant” because they run on physical server resources shared
   amongst other customers. This contrasts with Dedicated Hosts (e.g. from [3]),
   and is one of the reasons why Cloud Vendors can achieve high efficiency at
   “hyperscale” [47, 48, 60]. Other Compute units also exist, such as those sold
   through products like AWS Lambda or Google Cloud Functions. These are billed
   only whilst the code is executing with fees based on CPU and memory used over
   the (usually per hundred millisecond) execution time [32].
2. **Storage** exists in the form of arbitrarily sized disk volumes which can be
   attached to VMs, mimicking physical disk drives in servers. Different types of
   volume exist depending on the performance requirements e.g. solid-state disk
   (SSD) vs spinning disk [33]. Other types of storage are available, such as AWS
   Simple Storage Service (S3) which was one of the original cloud services
   launched in 2006 [2].
3. **Networking** links all the services together with internal and public data
   transfer from network interfaces attached to VMs through to virtual load
   balancers and firewalls. These exist as a Software Defined Network (SDN) as
   opposed to dedicated, physical devices for each customer.

Cloud Vendors also offer a range of other Software Services, such as Databases
and Queues. These are supporting infrastructure services used by customers in
their own applications but are built and maintained by the Cloud Vendor,
ultimately running on top of the Primitives. If a customer is using a Database
they are also making use of Primitives, but these are abstracted away so the
customer is unaware. This can be seen when a Primitive component suffers an
outage that then affects many other services which rely on it, such as the June
2019 GCP Networking Incident [31].

Just like their physical equivalents, Primitives run inside data centers located
in specific geographical regions operated by the Cloud Vendor. Customers can
choose in which region they wish to deploy their resources, and different
regions have different pricing e.g. an AWS EC2 t3.micro VM instance running in
N. Virginia, USA costs $0.0104/h whereas the same instance type running in
Sydney, Australia costs $0.0132/h [4]. Bandwidth costs also vary with some
regions being significantly more expensive than others e.g. data transfer in
Oceania is ×17 more expensive than Europe [58].

These Primitives are visible to the customer. It is the underlying physical
infrastructure that is hidden — the servers, disks, routing equipment housed
inside a cooled data center facility, powered by electricity. This means the
customer has no insight into the equipment lifecycle or the electricity required
to cool and power that equipment. This change from managing on-premise equipment
not only abstracts away the underlying infrastructure, it subsequently abstracts
the environmental impact caused by that equipment. For example, the location of
a data center has a strong relationship to energy usage due to local climate
conditions, seasonality, and the emissions factor of the power mix for the
electricity grid the data center is connected to [46].

To understand the full environmental impact of cloud environments, we must
consider all components that make up “cloud” services (Fig. 1).

![Fig 1: Public cloud components](/publications/2020-cloud-computing-assessing-ghg-fig1.png "Fig 1: Public cloud components")

## Using the GHG Protocol to assess cloud vendor emissions

The GHG Protocol Guidance for the ICT Sector [27] Section 4.5 provides an
accounting method for calculating GHG emissions related to data centers. This
section discusses whether the GHG Protocol is appropriate to assess Cloud Vendor
emissions.

### Assessment of GHG Protocol required primary data from the perspective of a cloud vendor customer

The tables below examine each primary data input required to calculate data
center emissions under the GHG Protocol Guidance for the ICT Sector [27]. This
shows that the guidance is appropriate from the perspective of the Cloud Vendor
but that this does not translate to the perspective of a Cloud Vendor customer.
The three largest Cloud Vendors by usage [22] – Amazon Web Services (AWS),
Microsoft Azure (Azure) and Google Cloud Platform (GCP) – are used to analyse
whether the data is available to Cloud Vendor customers.

The first column describes the data item as taken from the GHG Protocol
Guidance. The second column assesses whether this data is available from the
perspective of a Cloud Vendor customer.

GHG Protocol Description Data available to Cloud Vendor customers?
“use profiles and number of users at any given period of time” Yes – if relevant, this can be calculated based on application usage over a given period. Transactions may be an alternative (below).

**Table 1:** Availability assessment of primary data item - users - required under
the GHG Protocol for assessment of ICT emissions

| GHG Protocol Description                                       | Data available to Cloud Vendor customers?                                                                                                 |
| -------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| “use profiles and number of users at any given period of time” | **Yes** – if relevant, this can be calculated based on application usage over a given period. Transactions may be an alternative (below). |

**Table 2:** Availability assessment of primary data item - licensing or service level agreements - required under the GHG Protocol for assessment of ICT emissions

| GHG Protocol Description                                                                        | Data available to Cloud Vendor customers?                                                     |
| ----------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| “the units of service defined, for example, the number of users for a specified period of time” | **Yes** – if relevant, this can be calculated based on application usage over a given period. |

**Table 3:** Availability assessment of primary data item - transactions - required under the GHG Protocol for assessment of ICT emissions

| GHG Protocol Description                                                                                                                      | Data available to Cloud Vendor customers?                                                                                              |
| --------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| “for example, measured Iops (input-output operations per second) or WebAPIs/requests processed by the platform, over a specified time period” | **Yes** – if relevant, this can be calculated based on the application usage over a given period. Users may be an alternative (above). |

**Table 4:** Availability assessment of primary data item - data centers - required under the GHG Protocol for assessment of ICT emissions

| GHG Protocol Description | Data available to Cloud Vendor customers?                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| “number and location”    | **Partial** – the customer can determine which location (region) they deploy to, but the concept of “zones” cannot necessarily be mapped to a single data center. For example, Google Cloud Platform has the concept of Zones within Regions. The Region location is defined but the Zone location is not. A Zone may be one or many clusters where a cluster represents distinct physical infrastructure (power, cooling, network) within a data center. Further, zones are not necessarily physical, potentially differing across customers [34]. For certain types of Compute Primitives e.g. Azure Functions, code is deployed to a specific region but there may be multiple zones within the region and a zone may be one or many physical data centers [53]. AWS has a single region in Virginia [6] but has 55 physical data centers in that geography [19]. |

**Table 5:** Availability assessment of primary data item - server count - required under the GHG Protocol for assessment of ICT emissions

| GHG Protocol Description                                                                                                                                                        | Data available to Cloud Vendor customers?                                                                                                                                                                                                                                                                                                                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| “number of servers provisioned to host and fulfill the cloud application and data storage requirements. This includes redundancy for business continuity and disaster recovery” | **Partial** – the customer can determine which location (region) they deploy to. For VMs as Compute Primitives there is usually a one to one relationship between a VM running on (part of) a single physical server. However, it may not always be the same physical server if the VM is live migrated [35]. For other types of Compute Primitives e.g. Azure Functions, requests may be served across multiple servers. |

**Table 6:** Availability assessment of primary data item - network link equipment count - required under the GHG Protocol for assessment of ICT emissions

| GHG Protocol Description                                                                                                                                                                 | Data available to Cloud Vendor customers?                                                    |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| “number of in-data-center routers and switches required to fulfill WebAPI requests and process web transactions. This includes redundancy for business continuity and disaster recovery” | **No** – Cloud Vendor customers have no visibility of the underlying network infrastructure. |

**Table 7:** Availability assessment of primary data item - device utilisation - required under the GHG Protocol for assessment of ICT emissions

| GHG Protocol Description                                                           | Data available to Cloud Vendor customers?                                                                                                                                                                                                 |
| ---------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| “computational load that a device is managing relative to the specified peak load” | No – unless the customer selects to use dedicated hosts such as AWS/Azure Dedicated Hosts or GCP Sole-Tenant Nodes (and pays the additional costs), the Cloud Vendor provides no visibility of the utilization of the underlying devices. |

**Table 8:** Availability assessment of primary data item - power consumption by type of IT hardware - required under the GHG Protocol for assessment of ICT emissions

| GHG Protocol Description                                                                                                                | Data available to Cloud Vendor customers?                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| --------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| “calculated energy consumed by a server at a given rate of device utilization and estimated power for networking and storage equipment” | No – no information is available about the type of underlying hardware so no energy calculations can be completed. Indeed, “hyperscale” Cloud Vendors design many of their own hardware components [30, 50] with no publicly available power assessment. Some vendors have released their hardware designs under the open source Open Compute program, such as Microsoft’s Project Olympus [67]. This would allow independent assessment of the equipment power consumption but would require additional information about how this hardware is deployed into Microsoft Azure cloud environments. |

**Table 9:** Availability assessment of primary data item - data center power usage effectiveness (PUE) - required under the GHG Protocol for assessment of ICT emissions

| GHG Protocol Description                                                                                                                                                                                                                                                                       | Data available to Cloud Vendor customers?                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| “defined as the ratio of overall power drawn by the data center facility, to the power delivered to the IT hardware. This is a data-center-specific metric and accounts for energy consumption of active cooling, power conditioning, lighting, and other critical data center infrastructure” | Partial – industry average PUE is 1.67 [65]. AWS does not report PUE data but has a website footnote that states their internal-data shows PUE under 1.2 [5]. GCP reports their quarterly and trailing twelve-month (TTM) PUE values for “large-scale Google Data Centers”. For Q4 2019 fleet-wide TTM PUE was 1.10 with campus specific TTM PUE ranging of 1.07–1.15 [29]. However, this does not include all GCP Regions e.g. London and Tokyo are available regions but do not have published PUE data. Microsoft Azure does not report PUE data but states they “have met [their] goal of averaging 1.125 power usage effectiveness (PUE) for any new datacentre” [56]. |

**Table 10:** Availability assessment of primary data item - emission factors - equipment - required under the GHG Protocol for assessment of ICT emissions

| GHG Protocol Description                                                                                     | Data available to Cloud Vendor customers?                                                                            |
| ------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------- |
| “factors for the embodied emissions of relevant IT equipment, ideally obtained from equipment manufacturers” | **No** - no information is available about the type of underlying hardware so no emission factors can be calculated. |

**Table 11** Availability assessment of primary data item - emission factors - electricity - required under the GHG Protocol for assessment of ICT emissions

| GHG Protocol Description                                                                                                                                                                                                                                                                                                                                                                                                                    | Data available to Cloud Vendor customers?                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| “the emission factor for the electricity used should be appropriate for the region where the electricity is consumed. Electricity grid emission factors are published nationally, and in some cases, regionally. Electricity grid emission factors should include the full life cycle of the energy source (i.e., include emissions from extraction and transportation of the fuel, as well as generation and transmission of electricity)” | Partial – since actual electricity usage data is not provided by the Cloud Vendor, a regional average GHG emissions factor must be used [27]. Following the GHG Protocol Scope 2 Guidelines [26] would allow the factor to be determined. Each Cloud Vendor has a different electricity generation mix for each data center. For example, AWS reports that as of June 2015 the AWS “average power mix carbon intensity is 393 g/kWh” [12]. In 2015 Google reports a data center carbon intensity of 0.242 tCO2e/MWh which has reduced to 0.0495 tCO2e/MWh in 2018 [28]. Further, Google reports it has purchased 100% renewable energy to match its usage since 2017 [37]. However, a customer cannot complete the calculation unless the GHG emissions factor can be linked to activity. |

### Assessment of GHG Protocol required secondary data from the perspective of a cloud vendor customer

The GHG Protocol suggests using certain secondary data if the above primary
sources are unavailable: “Internet transfer” and “Embodied emissions for
hardware” [27].

#### Internet transfer and the network

Internet transfer is derived by using estimates of the energy intensity of the
internet: 0.06 kWh/GB for fixed line networks in 2015 [8]. This study also shows
this number decreasing by 50% every 2 years.

However, this only considers external traffic on the internet – it does not
account for internal network traffic which makes up a significant amount of data
transfer [42] and is doubling every 12–15 months [62]. Mobile traffic is another
significant exclusion when 71% of the global population expected to have mobile
connectivity by 2023 and smartphone traffic growing 7% annually [18]. Examining
mobile connectivity is an opportunity area for future research.

#### Embodied GHG emissions

“Embodied emissions for hardware” cannot be calculated without details of the
underlying hardware, which are not provided by any Cloud Vendor.

#### Data center capacity

Data center capacity is used in the GHG Protocol guidelines and consists of
calculating energy (in kWh) and capacity (in kilowatts or floor area). These
figures are not provided by Cloud Vendors.

A 2019 Greenpeace report [19] produced estimates of overall capacity in
Virginia, USA, one of the largest data center regions, by using Freedom of
Information requests to obtain backup generator permits, publicly reported lease
details and renewable energy deals. This approach allows an estimate of the
overall data center GHG emissions to be calculated for a specific geography, but
does not provide enough granularity for individual Cloud Vendor customers to
calculate their specific GHG emissions, particularly if deployed in different
regions around the world.

Using data center capacity to calculate GHG emissions for an individual customer
is not practical because capacity is shared by many customers even on a single
server within a single data center. This approach only works if customer
equipment takes up physical space in the data center (or the virtual
equivalent).

## Results

The GHG Protocol provides a methodology for assessing data center emissions but
it assumes that the assessor has access to various data inputs. The assessment
above demonstrates that these inputs are not available to Cloud Vendor
customers. This means that the GHG Protocol cannot be used by a Cloud Vendor
customer to calculate their GHG emissions – they do not have the data to do so.

GHG Protocol [27] Section 4.6.2 acknowledges that it is challenging to make
assessments in public cloud environments and suggests an alternative approach
based on estimates. However, it assumes the availability of data such as server
and VM totals e.g. “Estimated count of physical servers dedicated to the service
(divided by the total number of servers in the data center)”. Estimates have
been made for the emissions of entire facilities, such as the Greenpeace report
discussed in above. However, this does not allow calculations to be apportioned
on a per customer basis because server counts are unavailable. More granular
data is required.

The analysis above shows that data required to calculate emissions using the GHG
Protocol is only available to Cloud Vendors. One solution is for Cloud Vendors
to publish the required data so that customers can complete their own
calculations. Figures such as PUE have been released by some Cloud Vendors, as
discussed in Table 9, however these are too limited to satisfy the requirements
of the GHG Protocol. Most of the required data is considered a competitive
secret that is heavily guarded by Cloud Vendors. For example, Google has barred
public officials from releasing data about water usage which has resulted in
controversy in drought regions [59]. As a result, the GHG Protocol is not
appropriate for calculation of emissions from public cloud computing workloads
by Cloud Vendor customers.

If Cloud Vendors are not willing to release the underlying data, they must be
the ones to complete the calculations on behalf of their customers. The next
section will consider how a Cloud Vendor might approach this calculation.

## Calculating cloud vendor emissions per customer

All Cloud Vendors provide customers with access to detailed reporting about
their usage and the associated cost. By apportioning usage for billing purposes,
Cloud Vendors have demonstrated they can perform detailed resource accounting to
bill customers on a granular level. They can therefore do the same for
apportioning GHG emissions.

Several Cloud Vendors have demonstrated they have the underlying data needed to
calculate GHG emissions because they have produced marketing materials
containing competitive comparisons [1, 51] and/or aggregated data in annual
reports [28, 52]. Combined with the accounting mechanisms for billing, this
should allow Cloud Vendors to provide customers with an emissions report as
well. This section considers a conceptual approach for how such a report would
be constructed.

### Calculation inputs

The GHG Protocol assumes that all workloads run on physical servers within a
single data center, an assumption which does not hold in Cloud Vendor
environments. The framework in Fig. 1 can be used alongside the GHG Protocol
components discussed in section 3 to define the emissions boundary for each
customer on a per cloud product/service basis.

#### Example: virtual machine (VM)

A VM is deployed for a time period in a specific zone within a specific cloud
region. Cloud Vendor zones can be made up of one or more data centers [34, 53]
but this is not visible - the zone is the lowest level abstraction exposed to
customers. To provide a complete GHG emissions assessment, the Cloud Vendor
would need the following:

- Zone accounting: the time period each VM is running in each data center that
  makes up the zone within the region. VM pricing is usually based on CPU core
  and memory allocation by hour so the relevant functional unit for the zone
  accounting would be the same as the billing unit. A calculation would be
  produced for each data center then combined to provide the zone total.
- Emissions factors – equipment: the embodied emissions for the physical
  equipment (servers, racks, switches, etc) assigned to support the allocated
  CPU core and memory in each data center that makes up the zone within the
  region. This must consider the total fixed embodied emissions for the
  lifecycle of the equipment, and the utilisation of the equipment over the
  period so the total can be apportioned amongst all customers utilising that
  equipment. Although cloud vendors tend to have high utilisation rates, these
  are still lower than 50% [47, 48, 60].
- Emissions factors – electricity: each data center has its own energy mix,
  which will change dependent upon the local electricity grid. Zone accounting
  provides the date and time that each VM is running in each data center so the
  electricity emissions factors can be applied for the relevant period. A data
  center PUE calculation will allow the total electricity input to be
  apportioned between the fixed data center energy costs and the IT equipment.

#### Example: serverless function

Serverless functions are an emerging cloud computing technique [63] which allow
small units of code to be executed in response to events, only using resources
when they are triggered, and billed based on execution time in milliseconds.
This allows them to be very efficient by only running when needed, but
complicates accounting because it requires resources to be split into very small
units across physical resources. Serverless products from Amazon, Google and
Microsoft are deployed at a regional level which means for each instantiation a
serverless function could execute on a different server in a different data
center in a different zone.

This complicates emissions calculations and means the accounting mechanism needs
to track the execution across many physical devices. Once this has been achieved
the same approach as with a VM (4.1.1 above) would apply, but with the
functional unit changing to match the billing unit for the Cloud Vendor product.

### Calculation output

With the above data, a GHG emissions factor could be derived for each of the
Cloud Primitives on a usage basis e.g. Compute emissions in CO2 equivalent per
second of usage per Zone. Once assigned to the Primitives, all services based on
those Primitives can also provide a GHG emissions calculation. This would then
be combined by the existing usage and billing data to report total GHG emissions
to the customer.

### Microsoft sustainability calculator

In Jan 2020, Microsoft announced the availability of a “Sustainability
Calculator” [68] which allows customers of the Microsoft Azure cloud platform to
calculate the carbon emissions of their cloud resources.

Based on the methodology in a 2018 paper [51], Microsoft is applying the
approach described in GHG Protocol [27] using their internal data to provide a
value that can be reported by their customers under Scope 3 Category 1
emissions. The paper describes using the same inputs as above (section 4.1.1)
with the same boundaries shown in Fig. 1.

The Sustainability Calculator provides a geographic view of emissions by
calculating the local electricity carbon intensity for each region the customer
has deployed resources to. It considers the energy intensity of internet traffic
between Microsoft data centers and by third party connectivity. The 2018 paper
[51] uses the estimates in Aslan et al. [8] but it is not clear precisely which
value has been applied to the Sustainability Calculator e.g. has it been
adjusted to match the predicted decreases in the energy intensity.

Embodied emissions used by networking infrastructure outside of the specific
application were excluded from the 2018 paper model, so it is unclear if they
are included in the Sustainability Calculator. The calculator factors in
efficiencies gained from the utilisation, provisioning and multi-tenancy
benefits of cloud computing, however Microsoft has not released numbers
demonstrating what these values are. There is no indication that the efficiency
is better than the values provided by Masanet et al. [47, 48] and Shehabi et al.
[60]. Embedded emissions in the IT equipment (including the full lifecycle
emissions and disposal with a 20% recycle rate) are considered in the model but
are sourced from Masanet et al. [47, 48] rather than Microsoft equipment
specific values. Transportation of equipment is included in these estimates.
Embedded emissions in the building and cooling systems are excluded. Energy
during device utilisation is measured directly.

The result of the Sustainability Calculator is a number presented to the
customer measured in total metric tons of carbon dioxide equivalent (MTCO2e).
Gross emissions without offsets are indicated alongside a net figure which
includes the offsets purchased by Microsoft.

Microsoft has made the Sustainability Calculator available as an addon to its
PowerBI product [54]. Although the addon itself is free of charge, PowerBI is
not a free product and the Sustainability Calculator addon is only available to
Azure Enterprise customers [55]. As such, for the purposes of this paper the
calculator could only be tested using sample data only.

The Sustainability Calculator is an example of an implementation of the
conceptual approach described in this paper. It uses a published methodology
[51] and has been independently verified [68]. Within the Sustainability
Calculator user interface it notes:

> As part of the app’s development, the methodology and its implementation went
> through third-party verification to ensure that it aligns to the World
> Resources Institute (WRI)/World Business Council for Sustainable Development
> (WBCSD) Greenhouse Gas (GHG) Protocol Corporate Accounting and Reporting
> Standard. The scope of the verification, conducted in accordance with ISO
> 14064-3: Greenhouse gases -- Part 3: Specification with guidance for the
> validation and verification of greenhouse gas assertions, included the
> estimation of emissions from Azure service...

Whilst there are areas where additional transparency in the model and numbers
would be beneficial to be able to fully assess against the relevant literature,
and only certain “Enterprise” customers can access the Sustainability
Calculator, Microsoft is currently the only Cloud Vendor offering customer-level
reporting.

## Conclusion

The analysis in this paper has demonstrated that the GHG Protocol is not
suitable for customers to assess the emissions of their IT environments located
in the public cloud because the required information to calculate emissions is
not provided by Cloud Vendors.

The GHG Protocol makes assumptions about the availability of data such as IT
equipment embodied emissions and utilisation, which are not available to Cloud
Vendor customers. Where metrics are provided, such as PUE, these are not
published on a granular enough level due to how Core Primitives such as Compute
and Storage are sold to customers. For example, the precise data center location
is not revealed to Cloud Vendor Customers who instead are restricted to
visibility of a “zone” or “region” that does not necessarily map to a physical
facility. Even the secondary data suggested for use in cloud environments by the
GHG Protocol – estimated server counts for the workload and total number of
servers in the data center - are unavailable.

Further, the GHG Protocol only considers a single metric – PUE – in its
calculations. The criticisms of PUE discussed in section 1 show that other
metrics such as WUEsource, REF, ERF and equipment refresh rates are just as
important to understand the overall environmental footprint of a data center.
This all suggests that the GHG Protocol is no longer relevant in a world where
the majority of workloads are deployed in the cloud.

The solutions to this problem are limited. Transparency is necessary to assess
the environmental footprint of any product or service. The lack of data makes it
impossible for Cloud Vendor customers to comply with reporting requirements if
they wish to include Scope 3 emissions. Either Cloud Vendors must release all
the necessary data to allow customers to complete their own calculations or they
must perform the calculations on behalf of their customers. Given how secretive
the Cloud Vendors tend to be, the former is unlikely. As such, Cloud Vendors
will need to provide the calculations in a GHG Protocol compliant manner
instead.

Microsoft is the only Cloud Vendor offering this, having released a
Sustainability Calculator in January 2020. However, it is limited to a small
sub-set of customers.

To date, environmental sustainability has primarily been a marketing tactic for
Cloud Vendors. All the marketing materials suggest that moving to the cloud can
reduce your IT environmental footprint. Indeed, the big Cloud Vendors are the
largest purchasers of renewable energy, have the lowest PUE values and are
innovating with efficient, custom designed equipment. However, all this means
little until those efforts can be backed by environmental data.

Cloud Vendors have been able to ignore this to-date, keeping their environmental
efforts internal and vague. As climate risk increases, timely environmental data
will become just as important as accurate accounting information. Cloud Vendors
need to develop Sustainability Calculators available to all.

## Acknowledgements

Not applicable.

## Funding

None.

## Ethics declarations

### Competing interests

David Mytton has a financial interest in StackPath, LLC., an edge computing
company that has products which compete with those offered by the cloud vendors
mentioned in this paper.

## References

1. Accenture (2010) Cloud Computing and Sustainability: The Environmental
   Benefits of Moving to the Cloud. Available from:
   <https://download.microsoft.com/download/A/F/F/AFFEB671-FA27-45CF-9373-0655247751CF/Cloud%20Computing%20and%20Sustainability%20-%20Whitepaper%20-%20Nov%202010.pdf>
   [Accessed 21 Mar 2020]

2. Amazon. (2006) Amazon Web Services Launches. Available from:
   <https://press.aboutamazon.com/news-releases/news-release-details/amazon-web-services-launches-amazon-s3-simple-storage-service>
   [Accessed 21 Mar 2020]

3. Amazon. (2020c) Amazon EC2 Dedicated Hosts. Available from:
   <https://aws.amazon.com/ec2/dedicated-hosts/> [Accessed 21 Mar 2020]

4. Amazon. (2020d) Amazon EC2 Instance Pricing. Available from:
   <https://aws.amazon.com/ec2/pricing/on-demand/> [Accessed 21 Mar 2020]

5. Amazon. (2020e) AWS & Sustainability. Available from:
   <https://aws.amazon.com/about-aws/sustainability/> [Accessed 21 Mar 2020]

6. Amazon. (2020f) Regions, Availability Zones, and Local Zones. Available from
   <https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-regions-availability-zones.html>
   [Accessed 21 Mar 2020]

7. Andrae AS, Edler T (2015) On global electricity usage of communication
   technology: trends to 2030. Challenges 6(1):117–157.
   <https://doi.org/10.3390/challe6010117>

8. Aslan J, Mayers K, Koomey JG, France C (2018) Electricity intensity of
   internet data transmission: untangling the estimates. J Industrial Ecol
   22(4):785–798. <https://doi.org/10.1111/jiec.12630>

9. Avgerinou M, Bertoldi P, Castellazzi L (2017) Trends in data Centre energy
   consumption under the European code of conduct for data Centre energy
   efficiency. Energies 10(10):1470. <https://doi.org/10.3390/en10101470>

10. Bashroush R (2018) A comprehensive reasoning framework for hardware refresh
    in data centers. IEEE Transact Sustain Comput 3(4):209–220.
    <https://doi.org/10.1109/TSUSC.2018.2795465>

11. Bashroush R, Lawrence A (2020) Beyond PUE: tackling IT’s wasted terawatts.
    Uptime Institute Available from:
    <https://uptimeinstitute.com/beyond-pue-tackling-it’s-wasted-terawatts>
    [Accessed 11 June 2020]

12. Barr J (2015) Cloud computing, server utilization, & the environment. AWS
    News Blog Available from:
    <https://aws.amazon.com/blogs/aws/cloud-computing-server-utilization-the-environment/>
    [Accessed 21 Mar 2020]

13. Basmadjian R (2019) Flexibility-based energy and demand Management in Data
    Centers: A case study for cloud computing. Energies 12(17):3301.
    <https://doi.org/10.3390/en12173301>

14. Berl A, Gelenbe E, Di Girolamo M, Giuliani G, De Meer H, Dang M, Pentikousis
    K (2010) Energy-efficient cloud computing. Comput J 53(7):1045–1051.
    <https://doi.org/10.1093/comjnl/bxp080>

15. Berral JL, Goiri Í, Nguyen TD, Gavalda R, Torres J, Bianchini R (2014)
    Building green cloud services at low cost. In: 2014 IEEE 34th International
    Conference on Distributed Computing Systems, 30 June-3 July 2014. Madrid,
    Spain. IEEE:449–460. <https://doi.org/10.1109/ICDCS.2014.53>

16. Brady GA, Kapur N, Summers JL, Thompson HM (2013) A case study and critical
    assessment in calculating power usage effectiveness for a data Centre. Energ
    Conversion Manag 76:155–161.
    <https://doi.org/10.1016/j.enconman.2013.07.035>

17. Buyya R, Beloglazov A, Abawajy J (2010) Energy-efficient management of data
    center resources for cloud computing: a vision, architectural elements, and
    open challenges. arXiv 1006:0308 Available from:
    <https://arxiv.org/abs/1006.0308> [Accessed 21 Mar 2020]

18. Cisco (2020) Cisco Annual Internet Report (2018–2023) White Paper. Cisco
    Available from:
    <https://www.cisco.com/c/en/us/solutions/collateral/executive-perspectives/annual-internet-report/white-paper-c11-741490.html>
    [Accessed 21 Mar 2020]

19. Cook G, Jardim E, Craighill C (eds) (2019) Clicking Clean Virginia The Dirty
    Energy Powering Data Center Alley. Greenpeace Available from:
    <https://www.greenpeace.org/usa/reports/click-clean-virginia/> [Accessed 21
    Mar 2020]

20. Department for Business, Energy & Industrial Strategy (2018) Consultation
    outcome: Streamlined energy and carbon reporting. Available from:
    <https://www.gov.uk/government/consultations/streamlined-energy-and-carbon-reporting>
    [Accessed 21 Mar 2020]

21. Facebook (2020). Sustainability in numbers. Facebook. Available from:
    <https://sustainability.fb.com/sustainability-in-numbers/> [Accessed 11 Jun
    2020]

22. Flexera (2019) RightScale 2019 state of the cloud report from Flexera
    identifies cloud adoption trends. Flexera, Inc Available from:
    <https://www.flexera.com/about-us/press-center/rightscale-2019-state-of-the-cloud-report-from-flexera-identifies-cloud-adoption-trends.html>
    [Accessed 21 Mar 2020]

23. Forrester (2019) Forrester data: cloud security solutions forecast, 2016 to
    2021 (global). Forrester Research, Inc. Available from:
    <https://www.tatacommunications.com/wp-content/uploads/2019/02/Forrester-Report.pdf>
    [Accessed 21 Mar 2020]

24. Gao Y, Zeng Z, Liu X, Kumar PR (2013) The answer is blowing in the wind:
    analysis of powering internet data centers with wind energy. In: 2013
    Proceedings IEEE INFOCOM. IEEE, Turin, pp 520–524.
    <https://doi.org/10.1109/INFCOM.2013.6566827>

25. Gelenbe E (2012) Energy packet networks: adaptive energy management for the
    cloud. In: Proceedings of the 2nd International Workshop on Cloud Computing
    Platforms (CloudCP ‘12). Association for Computing Machinery, New York, pp
    1–5. <https://doi.org/10.1145/2168697.2168698>

26. GHG Protocol. (2015) GHG Protocol Scope 2 Guidance. Available from:
    <https://ghgprotocol.org/scope_2_guidance> [Accessed 21 Mar 2020]

27. GHG Protocol. (2017) ICT Sector Guidance built on the GHG Protocol Product
    Life Cycle Accounting and Reporting Standard. Available from:
    <https://ghgprotocol.org/sites/default/files/GHGP-ICTSG%20-%20ALL%20Chapters.pdf>
    [Accessed 21 Mar 2020]

28. Google (2019) Environmental report 2019. Google Available from:
    <https://services.google.com/fh/files/misc/google_2019-environmental-report.pdf>
    [Accessed 21 Mar 2020]

29. Google. (2020). Data Centers: Efficiency. Available from:
    <https://www.google.com/about/datacenters/efficiency/> [Accessed 11 Jun
    2020]

30. Google Cloud Platform (GCP). (2017) Google Infrastructure Security Design
    Overview: Hardware Design and Provenance. Available from:
    <https://cloud.google.com/security/infrastructure/design/#hardware_design_and_provenance>
    [Accessed 21 Mar 2020]

31. Google Cloud Platform (GCP). (2019) Google Cloud Networking Incident #19009.
    Available from:
    <https://status.cloud.google.com/incident/cloud-networking/19009> [Accessed
    21 Mar 2020]

32. Google Cloud Platform (GCP). (2020a) Google Cloud Functions Pricing.
    Available from: <https://cloud.google.com/functions/pricing> [Accessed 21
    Mar 2020]

33. Google Cloud Platform (GCP). (2020b) Block Storage Performance. Available
    from: <https://cloud.google.com/compute/docs/disks/performance> [Accessed 21
    Mar 2020]

34. Google Cloud Platform (GCP). (2020c) Regions and Zones. Available from:
    <https://cloud.google.com/compute/docs/regions-zones/> [Accessed 21 Mar
    2020]

35. Google Cloud Platform (GCP). (2020d) Live Migration. Available from:
    <https://cloud.google.com/compute/docs/instances/live-migration> [Accessed
    21 Mar 2020]

36. Heslin K (2016) Ignore data center Water consumption at your own peril.
    Uptime Institute; Weblog Available from:
    <https://journal.uptimeinstitute.com/dont-ignore-water-consumption/>
    [Accessed 11 Jun 2020]

37. Hölzle U (2018) Meeting our match: buying 100 percent renewable energy. The
    Keyword; Weblog Available from:
    <https://www.blog.google/outreach-initiatives/environment/meeting-our-match-buying-100-percent-renewable-energy/>
    [Accessed 21 Mar 2020]

38. Huusko J, de Meer H, Klingert S, Somov A (2012) Energy efficient data
    centers. Springer, Madrid. <https://doi.org/10.1007/978-3-642-33645-4>

39. International Standards Organisation (ISO). (2012) ISO/IEC DIS 30134–6
    Information technology — Data centres — Key performance indicators — Part 6:
    Energy Reuse Factor (ERF). Available from:
    <https://www.iso.org/standard/71717.html> [Accessed 11 Jun 2020]

40. International Standards Organisation (ISO). (2016) ISO/IEC 30134–2:2016
    Information technology — Data centres — Key performance indicators — Part 2:
    Power usage effectiveness (PUE). Available from:
    <https://www.iso.org/standard/63451.html> [Accessed 11 Jun 2020]

41. International Standards Organisation (ISO). (2018) ISO/IEC 30134–3:2016/AMD
    1:2018 Information technology — Data centres — Key performance indicators —
    Part 3: Renewable energy factor (REF) — Amendment 1. Available from:
    <https://www.iso.org/standard/72703.html> [Accessed 11 Jun 2020]

42. Jimenez M, Kwok H (2017) Building express backbone: Facebook’s new long-haul
    network. In: Facebook Engineering. Weblog Available from:
    <https://engineering.fb.com/data-center-engineering/building-express-backbone-facebook-s-new-long-haul-network/>
    [Accessed 21 Mar 2020]

43. Jones N (2018) How to stop data centres from gobbling up the world’s
    electricity. Nature 561(7722):163–167.
    <https://doi.org/10.1038/d41586-018-06610-y>

44. Kamiya, G., and Kvarnström, O. (2019) Data centres and energy – from global
    headlines to local headaches? Available from:
    <https://www.iea.org/commentaries/data-centres-and-energy-from-global-headlines-to-local-headaches>
    [Accessed 21 Mar 2020]

45. Lawrence A (2019) Is PUE actually going UP? Uptime Institute. Weblog
    Available from:
    <https://journal.uptimeinstitute.com/is-pue-actually-going-up/> [Accessed 11
    Jun 2020]

46. Lei N, Masanet E (2020) Statistical analysis for predicting
    location-specific data center PUE and its improvement potential. Energy 201.
    <https://doi.org/10.1016/j.energy.2020.117556>

47. Masanet E, Shehabi A, Koomey J (2013a) Characteristics of low-carbon data
    centres. Nat Climate Change 3(7):627–630.
    <https://doi.org/10.1038/nclimate1786>

48. Masanet E, Shehabi A, Ramakrishnan L, Liang J, Ma X, Walker B, Hendrix V,
    Mantha P (2013b) The energy efficiency potential of cloud-based software: A
    U.S. Case study. Lawrence Berkeley National Laboratory, Berkeley Available
    from: <https://eta.lbl.gov/publications/energy-efficiency-potential-cloud>
    [Accessed 21 Mar 2020]

49. Masanet E, Shehabi A, Lei N, Smith S, Koomey J (2020) Recalibrating global
    data center energy-use estimates. Science 367(6481):984–986.
    <https://doi.org/10.1126/science.aba3758>

50. Metz C (2016) Google’s making its own chips now. In: Time for Intel to freak
    out. Wired Available from:
    <https://www.wired.com/2016/05/googles-making-chips-now-time-intel-freak/>
    [Accessed 21 Mar 2020]

51. Microsoft. (2018a) The carbon benefits of cloud computing: A study on the
    Microsoft Cloud. Available from:
    <https://www.microsoft.com/en-gb/download/details.aspx?id=56950> [Accessed
    21 Mar 2020]

52. Microsoft. (2018b) 2018 Data Factsheet: Environmental Indicators. Available
    from: <http://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE3455q>
    [Accessed 21 Mar 2020]

53. Microsoft. (2019) What are Availability Zones in Azure? Available from:
    <https://docs.microsoft.com/en-gb/azure/availability-zones/az-overview>
    [Accessed 21 Mar 2020]

54. Microsoft. (2020a) Microsoft Sustainability Calculator. Available from:
    <https://appsource.microsoft.com/en-us/product/power-bi/coi-sustainability.sustainability_dashboard>
    [Accessed 21 Mar 2020]

55. Microsoft. (2020b) Connect the Microsoft Sustainability Calculator.
    Available from:
    <https://docs.microsoft.com/en-gb/power-bi/service-connect-to-microsoft-sustainability-calculator>
    [Accessed 21 Mar 2020]

56. Microsoft. (2020c) Azure global infrastructure. Available from:
    <https://azure.microsoft.com/en-us/global-infrastructure/> [Accessed 21 Mar
    2019]

57. Patterson M, Azevedo D, Belady C, Pouchet J (2011) Water Usage Effectiveness
    (WUE): A Green Grid Data Center Sustainability Metric. In: The Green Grid.
    White Paper number: 35 Available from:
    <https://www.thegreengrid.org/en/resources/library-and-tools/238-Water-Usage-Effectiveness-%28WUE%29%3A-A-Green-Grid-Data-Center-Sustainability-Metric>.
    [Accessed 11 Jun 2020]

58. Rao N (2016) Bandwidth costs around the World. In: The Cloudflare Blog.
    Weblog Available from:
    <https://blog.cloudflare.com/bandwidth-costs-around-the-world/> [Accessed 21
    Mar 2020]

59. Sattiraju N (2020) Google data centers’ secret cost: billions of gallons of
    Water. Bloomberg Green Available from:
    <https://www.bloomberg.com/news/features/2020-04-01/how-much-water-do-google-data-centers-use-billions-of-gallons>
    [Accessed 11 Jun 2020]

60. Shehabi A, Smith S, Sartor D, Brown R, Herrlin M, Koomey J, Masanet E,
    Horner N, Azevedo I, Lintner W (2016) United states data center energy usage
    report. Lawrence Berkeley National Laboratory, Berkeley Report number:
    LBNL-1005775. Available from:
    <https://eta.lbl.gov/publications/united-states-data-center-energy>
    [Accessed 21 Mar 2020]

61. Shehabi A, Smith SJ, Masanet E, Koomey J (2018) Data center growth in the
    United States: decoupling the demand for services from electricity use.
    Environ Res Lett 13:124030. <https://doi.org/10.1088/1748-9326/aaec9c>

62. Singh A, Ong J, Agarwal A, Anderson G, Armistead A, Bannon R, Boving S,
    Desai G, Felderman B, Germano P, Kanagala A (2015) Jupiter rising: A decade
    of clos topologies and centralized control in google’s datacenter network.
    ACM SIGCOMM Comp Commun Rev 45(4):183–197.
    <https://doi.org/10.1145/2785956.2787508>

63. Spiceworks (2019) 2019 State of IT. Spiceworks Available from:
    <https://www.spiceworks.com/marketing/state-of-it-2019/future-tech/>
    [Accessed 21 Mar 2020]

64. UNESCO World Water Assessment Programme (2020) The United Nations world
    water development report 2020: water and climate change. UNESCO, Paris
    Available from:
    <https://unesdoc.unesco.org/ark:/48223/pf0000372985.locale=en> [Accessed 11
    Jun 2020]

65. Uptime Institute (2019) Annual Data Center Survey Results. Uptime Institute
    Available from:
    <https://uptimeinstitute.com/resources/asset/2019-data-center-industry-survey>
    [Accessed 21 Mar 2020]
66. Van Heddeghem W, Lambert S, Lannoo B, Colle D, Pickavet M, Demeester P
    (2014) Trends in worldwide ICT electricity consumption from 2007 to 2012.
    Comp Commun 50:64–76. <https://doi.org/10.1016/j.comcom.2014.02.008>

67. Vaid K (2016) Microsoft reimagines open source cloud hardware. Microsoft
    Azure Blog: Weblog Available from:
    <https://azure.microsoft.com/en-gb/blog/microsoft-reimagines-open-source-cloud-hardware/>
    [Accessed 21 Mar 2020]

68. Walshe N (2020) Microsoft sustainability calculator helps enterprises
    analyze the carbon emissions of their IT infrastructure. Microsoft Azure
    Blog; Weblog Available from:
    <https://azure.microsoft.com/en-gb/blog/microsoft-sustainability-calculator-helps-enterprises-analyze-the-carbon-emissions-of-their-it-infrastructure/>
    [Accessed 21 Mar 2020]

69. Webster, B. (2019) Behind the manifestos: How green is my party? The Times.
    Available from:
    <https://www.thetimes.co.uk/article/behind-the-manifestos-how-green-is-my-party-t26lzjgzn>
    [Accessed 21 Mar 2020]

70. Whitehead B, Andrews D, Shah A, Maidment G (2014) Assessing the
    environmental impact of data centres part 1: background, energy use and
    metrics. Build Environ 82:151–159.
    <https://doi.org/10.1016/j.buildenv.2014.08.021>
