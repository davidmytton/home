---
title: "Sustainable Computing"
date: 2017-12-01
modified: 2022-10-29
showDate: false
showDateUpdated: true
showAuthor: false
draft: false
summary: "A set of resources about sustainable computing. What is sustainable 
computing? Articles, communities, data, papers, reports, tools."
---

My area of research interest could be broadly called “sustainable computing”,
which I am actively pursuing in the [Department of Engineering
Science](https://eng.ox.ac.uk/) at the [University of
Oxford](https://www.ox.ac.uk/). I maintain this page as a set of resources about
sustainable computing that I find useful.

### What is sustainable computing?

Sustainable computing concerns the consumption of computing resources in a way
that means it has a net zero impact on the environment, a broad concept that
includes energy, ecosystems, pollution and natural resources.

I consider that individual impact on the environment rounds to zero because
although some people will change their behaviour, most won’t. This means that
systems need to change. Energy production, transportation, manufacturing,
agriculture. The transition to sustainability needs to be done on behalf of the
individual by the system and at a large scale, so individuals can benefit from
that change by default.

In computing, this means the organisations responsible for manufacturing
components, building equipment, writing software, operating data centres, and
running networks have responsibility for achieving sustainability.

Sustainability strategies in computing tend to focus on energy and the
transition to renewables – the use stage. This is important, but not the only
factor.

Sustainable computing therefore involves not just renewable energy, but also
minimising water stress, developing policies around the right to repair and
recycling of materials through a circular economy, energy efficiency of hardware
and software, promoting good governance of resources, transparency, and
consistent reporting.

### Articles

- **[Estimating AWS EC2 Instances Power
  Consumption](https://medium.com/teads-engineering/estimating-aws-ec2-instances-power-consumption-c9745e347959)**.
  This writeup explains a pragmatic approach to figuring out the energy
  consumption of AWS EC2 images. It uses measurements and some reverse
  engineering to build profiles for some common instance types, and reveals
  issues with relying on the [SPECpower
  dataset](https://www.spec.org/power_ssj2008/results/) (mentioned below).
- [**Building an AWS EC2 Carbon Emissions
  Dataset**](https://medium.com/teads-engineering/building-an-aws-ec2-carbon-emissions-dataset-3f0fd76c98ac).
  A followup to the above post to add embodied emissions calculations to EC2
  instances. In Dec 2021 I implemented this methodology into the Cloud Carbon
  Footprint project as part of the [cloud carbon
  coefficients](https://github.com/cloud-carbon-footprint/cloud-carbon-coefficients) calculations.

### Communities

- [**ClimateAction.tech**](https://climateaction.tech/). I subscribe to this
  weekly newsletter because it provides a good summary of interesting news,
  events and podcasts related to what the technology sector can do to help
  climate change. I’m not in the Slack group though because I try and [avoid
  group chat](https://m.signalvnoise.com/is-group-chat-making-you-sweat/) [where
  possible](https://blog.console.dev/console-culture-considered-discussion/).
- **[Green Software Foundation](https://greensoftware.foundation/)**. A group of
  technologists (primarily from commercial organizations) working on standards
  and best practices to help software developers build more sustainable
  software.

### Data

Interesting sources of data related to sustainable computing:

- **[Cambridge Bitcoin Electricity Consumption Index](https://cbeci.org/)**. The
  headline figure is 97 TWh of annualised energy consumption, but with a range
  of 35 TWh – 364 TWh. However the missing context is how that electricity is
  generated. Distinguishing between whether that came from fossil fuels or
  renewables is important ([39% renewables, primarily
  hydro](https://www.jbs.cam.ac.uk/faculty-research/centres/alternative-finance/publications/3rd-global-cryptoasset-benchmarking-study/)),
  particularly as governments impose stricter regulations which may have
  unintended negative effects ([such as increasing carbon intensity of
  mining](https://dx.doi.org/10.1016/j.joule.2022.02.005)). Whether it is
  possible to move to a proof-of-stake implementation, [like
  Ethereum](https://ethereum.org/en/developers/docs/consensus-mechanisms/pos/),
  is also important.
- [**Carbon free energy for Google Cloud
  regions**](https://cloud.google.com/sustainability/region-carbon). Google is
  the leader in sustainable cloud computing. They have done the most work and
  made the most progress at reaching carbon neutrality, then 100% renewables
  matching, and have a goal to hit 24/7 renewables by 2030. They are less
  transparent on water consumption, but do publish data on their carbon free
  energy percentage for each GCP region.
- **[SPECPower database](https://www.spec.org/power_ssj2008/results/)**. The
  Standard Performance Evaluation Corporation (SPEC) provides quarterly test
  results of the power and performance of the latest single and multi-node
  servers. By simulating workloads, this data shows the average power
  consumption (in watts) at 100% and idle load. The difference between the two
  is known as power proportionality – does the server reduce its power
  consumption in proportion to the load – a ratio which has been improving over
  time. This data is used as part of the [cloud carbon
  coefficients](https://github.com/cloud-carbon-footprint/cloud-carbon-coefficients) project
  to provide estimates for the power consumption of popular cloud computing CPUs
  for use in the **[Cloud Carbon
  Footprint](https://www.cloudcarbonfootprint.org/)** project.

### Papers

Interesting academic papers related to sustainable computing:

- **[The environmental footprint of data centers in the United
  States.](https://doi.org/10.1088/1748-9326/abfba1)** *Environmental Research
  Letters.* (2021). This paper discusses the wider impact of data centres but
  has some major water-related findings. They show that 1/5th of direct water
  footprint (for cooling) comes from moderate to high stress watersheds, and
  that nearly half of power generation is sourced from power plants in water
  stressed regions. This is an important analysis showing the impact of indirect
  water consumption through energy generation. See also: [How much water do data
  centers use?](https://davidmytton.blog/how-much-water-do-data-centers-use/)
- **[Recalibrating global data center energy-use
  estimates](https://doi.org/10.1126/science.aba3758).** *Science*. (2020). This
  paper represents the current best figures of global data centre energy
  consumption from the perspective that energy growth has plateaued. They
  estimate data centres consumed 196 TWh of energy in 2020. Their system
  boundaries exclude cryptocurrencies and make some major assumptions about the
  migration to hyperscale cloud (AWS, Google, Microsoft).
- **[Green Cloud?](https://doi.org/10.2991/ict4s-16.2016.13)** *Advances in
  Computer Science Research* (2016). This paper represents the other end of the
  credible data centre energy estimates, placing data centre energy consumption
  at 287 TWh in 2015. Their system boundaries do include crypto. See also
  subsequent papers from the same authors: [Energy consumption of data centers
  worldwide](http://ceur-ws.org/Vol-2382/ICT4S2019_paper_16.pdf) (2019)
  and [Efficiency gains are not enough: Data center energy consumption continues
  to rise significantly](https://dx.doi.org/10.13140/RG.2.2.26033.40800) (2020)
  with the last of these providing an estimate for 400 TWh for 2020.
- **[Electricity Intensity of Internet Data Transmission: Untangling the
  Estimates](http://doi.wiley.com/10.1111/jiec.12630).** *Journal of Industrial
  Ecology* (2018). This is the latest calculation of fixed-line network energy
  intensity i.e. the energy consumption of data transmission. The figure for
  2015 is 0.06 kWh/GB with a projection that this figure will fall by 50% every
  2 years. The notable aspect of this system boundary is that it excludes mobile
  devices.

See also [my own publications](/publications/).

### Reports

Interesting reports related to sustainable computing:

- **[Clicking Clean
  Virginia](https://www.greenpeace.org/usa/reports/click-clean-virginia/),
  Greenpeace (2019)** Greenpeace are often seen as extremists but they do a good
  job of raising awareness. In this report they attempt to estimate energy
  consumption of data centers in Virginia, US, particularly those used by cloud
  providers like Amazon, Google and Microsoft. They use FOI requests to obtain
  local permits for facility sizes and then estimate the total energy demand
  depending on the size of the data center. The energy supplier for Virginia is
  notorious for using fossil fuels and so Greenpeace does a good job of laying
  those alongside the “100% renewable energy” claims made by the big providers.
  See also: [How can data centers use 100% renewable
  electricity?](https://davidmytton.blog/how-can-data-centers-use-100-renewable-electricity/)
- **[Digital technology and the planet](https://royalsociety.org/-/media/policy/projects/digital-technology-and-the-planet/digital-technology-and-the-planet-report.pdf),
  Royal Society (2020)** A wide-ranging report from the Royal Society. Chapters
  2 and 3 are of particular interest in relation to better disclosures and the
  impact of technology use.

### Tools

Interesting tools related to sustainable computing:

- **[Carbon Aware
  SDK](https://github.com/Green-Software-Foundation/carbon-aware-sdk)** An open
  source CLI and JSON API to get carbon data into your applications. Written in
  C#.
- **[Cloud Carbon Footprint](https://www.cloudcarbonfootprint.org/)**: This is
  an open-source software project led
  by [Thoughtworks](https://www.thoughtworks.com/) that connects to your cloud
  billing account and runs estimates on the kWh and associated CO2 from the
  resources you are using. I have made several code contributions to the core
  project, including implementing the [cloud carbon
  coefficients](https://github.com/cloud-carbon-footprint/cloud-carbon-coefficients) methodology
  as a self-contained project that is regularly updated from server power
  consumption test data.
- [**CodeCarbon**](https://mlco2.github.io/codecarbon/): Takes readings from AMD
  and Intel CPUs every 15s to provide energy consumption reporting mapped to
  carbon intensity.
- **[Coppers](https://github.com/ThijsRay/coppers)**: A test harness for Rust
  that will measure the energy consumption of test runs using the RAPL API.
- **[Datavizta](https://datavizta.boavizta.org/)**: Open database of carbon
  impact factors for computer equipment – laptops, monitors, servers, etc.
  Also [available on
  GitHub](https://github.com/Boavizta/environmental-footprint-data).
- **[Electric Insights](https://electricinsights.co.uk/)**: Not sustainable
  computing specific but I use this on a regular basis to provide data about how
  the grid mix changes. It’s built and maintained by one of my supervisors at
  Imperial College London.
- [**EAM Environmental Modelling and Assessment
  Toolkit**](https://github.com/sust-cs-uob/eam-core): Presented at the ACM
  SIGCAS/SIGCHI Conference on Computing and Sustainable Societies (COMPASS)
  and [described in the related
  paper](https://dl.acm.org/doi/10.1145/3530190.3542933), but the repo is very
  sparse and has no instructions or documentation.
- [**greeNsort**](https://greensort.eu/index.html): A set of more efficient
  sorting algorithms that claims to be significantly more energy efficient. Lots
  of interesting reading on the website, but the code is not open source and is
  not available to download or use without buying a license.
- [**Scaphandre**](https://github.com/hubblo-org/scaphandre): An open source
  tool (written in Rust) that is designed to introspect power consumption from a
  bare metal host and/or Qemu/KVM VMs running on a host in a way that they can
  be graphed using common tools like Prometheus and Grafana. [Only supports
  Intel CPUs](https://github.com/hubblo-org/scaphandre/issues/46).
- **[PowerJoular](https://gitlab.com/joular/powerjoular):** Very similar to
  Scaphandre, but written in Ada and for Linux. Supports analyzing RAPL CPUs
  from Intel (Sandy Bridge onwards) and AMD (Ryzen onwards). Can also examine
  NVIDIA GPUs.
- [**Software Carbon Intensity
  (SCI)**](https://github.com/Green-Software-Foundation/software_carbon_intensity):
  This is a specification for how to calculate a score that indicates the carbon
  intensity of software, produced by the [Green Software
  Foundation](https://greensoftware.foundation/). It’s not yet released as a
  stable spec and I have some concerns about how [scores can be
  compared](https://github.com/Green-Software-Foundation/software_carbon_intensity/discussions/208) and [why
  infrastructure measures have been
  excluded](https://github.com/Green-Software-Foundation/software_carbon_intensity/discussions/207).
- [**Tools to measure software energy
  consumption**](https://luiscruz.github.io/2021/07/20/measuring-energy.html): A
  good blog post that explains several methods for measuring how much energy is
  being consumed by your computer.
- [**Website power consumption measurement in
  Firefox**](https://www.green-coding.org/blog/firefox-104-energy-measurements/) ([my
  blog post on
  this](https://davidmytton.blog/measuring-website-energy-consumption/)): Added
  in Firefox 104, you can now view power consumption stats on Windows ([Windows
  10 if there is an energy metering interface or Windows 11 via
  RAPL](https://docs.microsoft.com/en-us/windows-hardware/drivers/powermeter/energy-meter-interface))
  and Mac (Apple Silicon only). [See the implementation
  log](https://bugzilla.mozilla.org/show_bug.cgi?id=1774844) and [Windows](https://hg.mozilla.org/mozilla-central/rev/185ab81e5f51) and
  [Mac](https://hg.mozilla.org/mozilla-central/rev/0839b2f7ae02) changesets.
  This provides output in watts in the profiler UI, but the internals
  are [measuring in
  picowatt-hour](https://hg.mozilla.org/mozilla-central/file/tip/tools/profiler/core/PowerCounters-mac.cpp#l35).
  On Mac it’s using the [task_info
  API](https://github.com/apple/darwin-xnu/blob/8f02f2a044b9bb1ad951987ef5bab20ec9486310/osfmk/mach/task_info.h#L464).
  Also worth mentioning the [Firefox powermetrics
  guide](https://firefox-source-docs.mozilla.org/performance/powermetrics.html) which
  describes the measurement tools available in the Firefox source code.

### Other

- [**Awesome Green
  Software**](https://github.com/Green-Software-Foundation/awesome-green-software):
  A list of dev/tooling, organizations and research/articles about how software
  developers can approach building software in a more sustainable way.
- [**Adrian Cockcroft’s talk at Monitorama
  2022**](https://www.youtube.com/watch?v=pt-QATPyuhs&t=25626s): Recently
  retired AWS VP, Sustainability, Adrian Cockcroft, gave a good 30min talk at
  the [Monitorama 2022 conference](https://monitorama.com/2022/pdx.html): where
  he summarised the state of cloud carbon sustainability. Nothing new if you
  already know the topic, but a great intro to the current state of things.
- [**Hot Carbon 2022**](https://hotcarbon.org/): A conference/workshop all about
  sustainable computing, with videos and papers for most of the talks.
- [**Principles of Green Software Engineering**](https://principles.green/): A
  set of principles for software engineers to keep in mind when writing software
  to try and reduce its environmental impact (which usually means carbon, but
  isn’t limited to that being the only measure).
