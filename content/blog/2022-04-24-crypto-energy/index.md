---
title: "How much energy does cryptocurrency use?"
date: 2022-04-24
modified: 2022-04-24
draft: false
tags: ["Data Center Energy", "IT Energy", "Energy Efficiency"]
summary: "Is cryptocurrency / Bitcoin bad for the environment? In 2019 crypto 
consumed 70-90 TWh of electricity globally, with 60-70 TWh of that from Bitcoin 
mining. What that means for carbon emissions depends on where the mining 
happens."
url: how-much-energy-does-cryptocurrency-use
---

[It is estimated](https://dx.doi.org/10.13140/RG.2.2.26033.40800) that in 2019
cryptocurrencies consumed 70-90 TWh of electricity globally, with 60-70 TWh of
that from Bitcoin mining. In comparison, [all data centers worldwide used
between 196-400 TWh of energy in
2020](https://davidmytton.blog/how-much-energy-do-data-centers-use/) (although
the latter figure includes some crypto).

However, these numbers are quite uncertain. Some calculate a range of [60 TWh –
204 TWh for
Bitcoin](https://digiconomist.net/bitcoin-energy-consumption) and [17 TWh – 105
TWh for Ethereum](https://digiconomist.net/ethereum-energy-consumption) (as of
Apr 2022) and there are many hundreds of crypto assets, all with different
energy profiles.

[Analysis of these other
assets](https://doi.org/10.1016/j.joule.2020.07.013) suggest that Bitcoin is
responsible for ~66% of all crypto-related energy consumption, with the variance
in energy consumption related to whether the hashing algorithm can be run on
specialist equipment or not.

![Table of the top cryptocurrencies and their energy
consumption](top-crypto-by-market-cap.png "The top 20 mineable currencies with
their respective algorithms, efficiencies of suitable mining devices, and rated
power of the networks (as of 2020-03-27). **Source:** [Gallersdörfer, U.,
Klaaßen, L., and Stoll, C. (2020). Energy Consumption of Cryptocurrencies Beyond
Bitcoin. Joule](https://dx.doi.org/10.1016/j.joule.2020.07.013).")

Electricity is the main energy input into crypto mining so the changing grid mix
throughout the day has an impact on the carbon footprint of the cryptocurrency
being mined. This means that just like with manufacturing physical products, the
country where the cryptocurrency is mined makes a difference.

[In 2019, 44% of Bitcoin mining was happening in
China](https://dx.doi.org/10.1016/j.joule.2022.02.005) and around [39% of all
proof-of-work cryptocurrencies were mined with renewable energy, primarily
hydro](https://www.jbs.cam.ac.uk/faculty-research/centres/alternative-finance/publications/3rd-global-cryptoasset-benchmarking-study/).
However, in May 2021 China cracked down on Bitcoin which resulted in the halt of
almost all mining activities in the country. Moving elsewhere, they inherited
the grid mix of the countries they moved to. [This resulted in the overall
carbon footprint increasing](https://dx.doi.org/10.1016/j.joule.2022.02.005):

> Based on average emission factors (557.76 gCO2/kWh) and the Bitcoin network’s
> estimated electric load demand (13.39 GW as of August 2021), we estimate that
> Bitcoin mining may be responsible for 65.4 megatonnes of CO2 (MtCO2) per year.
>
> <cite>[de Vries, A., Gallersdörfer, U., Klaaßen, L., and Stoll, C. (2022).
> Revisiting Bitcoin’s carbon footprint.
> Joule](https://dx.doi.org/10.1016/j.joule.2022.02.005).</cite>

This is equivalent to around 0.19% of global emissions, the same as Greece.

![Illustration of Bitcoin energy fuels](bitcoin-fuels.png "Estimated electricity
mix that fuelled the Bitcoin network from September 2019 to August 2021.
**Source:** [de Vries, A., Gallersdörfer, U., Klaaßen, L., and Stoll, C. (2022).
Revisiting Bitcoin’s carbon footprint.
Joule](https://dx.doi.org/10.1016/j.joule.2022.02.005).")

## Crypto mining equipment waste

Crypto mining has become a specialist activity that is performed on dedicated
equipment designed for the job. Unlike more general IT equipment, there is a
direct and urgent economic incentive for miners to always use the most efficient
equipment. As efficiency doubles every 1.5 years ([Koomey’s
Law](https://doi.org/10.1109/MAHC.2010.28)), Bitcoin mining equipment [becomes
obsolete at the same rate](https://doi.org/10.1016/j.joule.2019.02.007).

When buying a new consumer laptop, [most of the carbon footprint is in the
manufacturing](https://davidmytton.blog/carbon-footprint-laptops-vs-servers-intel-vs-arm/).
The opposite is true for servers – most of the carbon footprint comes from
operating it. You get the worst of both worlds with crypto mining equipment –
you combine the high manufacturing emissions with high energy consumption during
the use stage, then it becomes useless within just 1.5 years.

[Calculations](https://doi.org/10.1016/j.joule.2019.02.007) about useful life of
Bitcoin equipment across the whole network in 2018 suggested that each
transaction generated 134.5 g of electronic waste, compared to 0.0045 g per Visa
transaction. There are lots of assumptions in this calculation, and it is
several years old, but for Bitcoin to be as efficient as Visa as a method of
transaction would require improvements of several orders of magnitude.

## Challenges with calculating cryptocurrency mining energy consumption

The amount of energy required varies significantly depending on the type of
underlying technology. In proof-of-work assets like Bitcoin, calculations are
performed to create new blocks, which mint new Bitcoins. Those calculations
consume computing power, which is where the energy is used. The reward for
performing the calculations is the value of the minted Bitcoin.

The hash rate can be used to track the number of calculations happening at any
given time – currently averaging near an all time high of around ~200 million
terahashes/sec. The amount of energy required per hash is not constant – it is
based on the computational difficulty, [which varies per
block](https://doi.org/10.1038/s41558-018-0321-8) – but each computation
requires energy, so the greater the computational rate, the greater the energy
consumption. This is the “proof-of-work”.

Not all cryptocurrencies involve mining and there are efforts to transition
some, like Ethereum, to less energy-intensive methods
([proof-of-stake](https://ethereum.org/en/developers/docs/consensus-mechanisms/pos/)). [The
official
position](https://blog.ethereum.org/2021/05/18/country-power-no-more/) is that
moving Ethereum to proof-of-stake will reduce its energy consumption by 99.95%.

![Graph of Bitcoin hash rate](bitcoin-hashes.png "Estimated number of terahashes
per second the bitcoin network.
From [Blockchain.com](https://www.blockchain.com/charts/hash-rate).")

Asset prices are another important factor because this determines how much can
be spent on mining energy:

> Bitcoin’s price directly effects the value of the mined coins and therefore
> the amount of resources miners can afford to spend on mining. Given that
> Bitcoin mining is a competitive market, economic theory suggests that it
> should cost a bitcoin to mine a bitcoin. If it costs any less than one bitcoin
> to mine a bitcoin, miners can profit by adding more units of computational
> power to the network. The opposite is also true because miners would be
> operating at a loss and start removing units of computational power from the
> network if mining costs exceed one bit-coin.
>
> <cite>[de Vries, A. (2021). Bitcoin boom: What rising prices mean for the
> network’s energy consumption.
> Joule](https://dx.doi.org/10.1016/j.joule.2022.02.005).</cite>

Therefore, annualized energy consumption will increase as the price increases.
Placing a bet on the appreciation of the price of a particular proof-of-work
crypto asset is implicitly betting that the energy consumption will
increase. [Although it is as difficult to
predict](https://doi.org/10.1038/s41558-018-0321-8) the energy consumption as it
is to predict the asset price, [as hash rates have generally trended
up](https://doi.org/10.1038/s41893-018-0152-7) we can assume that energy
consumption will also continue to increase.

## Is cryptocurrency / Bitcoin bad for the environment?

Answering this question requires you to make a judgment about the utility of a
specific crypto asset, or crypto as a whole. I am generally very skeptical about
most crypto assets, particularly NFTs in the form they exist today. It feels
like most “investors” are actually just speculating on a future price increase
and the communities around them act like cults. [There are concerning
examples](https://web3isgoinggreat.com/) of fraud and major security breaches,
and the major innovation in digital technology is the idea of abundance and zero
marginal cost whereas the value in many cryptocurrencies is from scarcity.

However, I appreciate the value of decentralization, individual ownership, and
the idea of self-custody of assets (assuming the UX is well designed and
individuals can manage their security correctly). It is difficult to cut through
the noise and figure out if this is indeed [like the early days of the
internet](https://www.bloomberg.com/news/articles/2021-06-24/andreessen-launches-2-2-billion-crypto-fund-after-bitcoin-crash) or
whether the whole thing is just a massive collection of Ponzi schemes.

We are used to the idea of consuming energy for something useful. It’s not
correct to ask “is the internet bad for the environment” or “is video streaming
bad for the environment”. Rather, we should ask “what is the environmental
impact of internet usage” or “what impact does video streaming have on the
environment”. We have decided that both the internet and video streaming are
useful – the question is how do we minimize their environmental impact? This is
why I spend time working on [sustainable
computing](https://davidmytton.blog/sustainable-computing/) – computer
technology is a net good, so how do we make it sustainable so that more people
can benefit?

So when someone asks: is crypto / Bitcoin / blockchain / Etherum bad for the
environment? We should first question whether there is any usefulness in the
technology itself. If there is utility, we can consider how to minimize its
impact. If not, then we should be thinking about how to minimize the use of the
technology itself.

Given how long crypto has been around, and how much money has gone into it, I
find it unlikely that it will all suddenly disappear. Also remember the [Jevons
paradox](https://en.wikipedia.org/wiki/Jevons_paradox) – if something is made
more efficient then it will use more energy, not less. Bitcoin may not be the
end game – I expect (and hope) more interesting use cases will be developed –
but crypto (and web3) is here to stay. That means work needs to be done to make
it sustainable.
