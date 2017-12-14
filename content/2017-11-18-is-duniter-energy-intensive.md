Title: Is Duniter energy consuming ?
Date: 2017-11-18
Category: Technical
Tags: proof of work
Slug: is-duniter-energy-consuming
Authors: cgeek
Thumbnail: /images/light. svg

The Bitcoin has a reputation for being an energy consuming. Duniter inherits some of the Bitcoin's properties, such as the proof of work and the blockchain. People are therefore legitimately asking this question: 

> Is Duniter also energy consuming ?

### A little bit of definition

First of all, we should focus on the term *energy consuming*. But just about any system is energy-consuming, for example our human cells. This definition is not the problem, as it is readily understood that Bitcoin or Duniter requires energy to function.

On the other hand, one might think that this is a quantity problem: for example, 10 Wh is less than 10 kWh by a factor of 1000. Yes, but is 10 kWh a lot?

### A connection to other uses

As such, we are unable to say that "10 kWh is a lot". On the other hand, we could say "10 kWh is a lot of energy if it's just to produce light for 1 hour in my living room". Indeed, today a 100 W bulb (even an old generation) would be more than enough to illuminate a living room of 50m² and would consume only 100 Wh in one hour (by definition), and so we are far from 10 kWh: it is 100 times less!

This is my point: a system is said to be "energy-intensive" **in relation to the service provided**, and therefore in comparison with other uses of the same amount of energy.

For example, in the case of Bitcoin, [each transaction consumes 215 kWh](https://digiconomist.net/bitcoin-energy-consumption). What can you do with that much energy? The equivalent of 32 days of electricity consumption for an average French person can be provided. This may sound high to simply perform *a single bitcoin transfer*. Bitcoin makes 300,000 transactions *per day*. I'll let you do your math.

> Yes, it's *a lot*! Relative to other possible uses of this same amount of energy.

### And Duniter in all this?

A first point to understand is that there is no race for power in Duniter, **for the simple reason that there is no particular reward to calculate blocks** unlike the Bitcoin. This simple measure cuts the grass under the foot of a possible run.

However, Duniter does have a proof-of-work mechanism to allow network nodes to speak synchronously. This task is the source of Bitcoin's energy consumption. But here again, Duniter benefits from unique mechanisms because of its web of trust: first, only members of the currency can calculate blocks, which limits the number of potential participants. But also, Duniter has a mechanism *that permanently excludes 1/3 of the computer network from proof of work*. This means that at each block there are 1/3 of the computers that turn their thumbs. And so, only 2/3 of them actually make calculations. This excluded 1/3 can then adjust its power consumption to perform only simple operations, such as receiving transactions on the network.

<center><image src="../images/networking.svg" width="200px"/></center>

Does this mean that the remaining 2/3 of the electricity consumption is high? Contrary to the Bitcoin, the machines used for calculation are home computers, possibly servers or simply Raspberry PI. And all that is enough. Besides, Bitcoin's ultra-efficient machines (the famous[ASIC](https://en.bitcoin.it/wiki/ASIC)] are totally useless in Duniter because the proof of work mechanism is not the same.

**And so in reality, each Duniter node consumes as much energy as a bulb of 10 W to 100 W, which runs continuously.**

<center><image src="../images/light.svg" width="200px"/></center>

### How much is that for the Ğ1 ?

Today the Ğ1 has about 30 member nodes that calculate blocks. If an average of 55 W of instantaneous consumption per node is counted, then `55*24 = 1.32 kWh` of electricity consumption per day per node, or `1.32*30 = 39.6 kWh` of total grid consumption per day.

Is that a lot? We now have about 12 transactions per day. It may seem high to have 30 light bulbs of 55 W on at all times just to make 12 transactions a day.

Yes, but there is nothing to prevent you from increasing to 120 transactions per day with the same network size. Duniter is currently under-registered, 120 transactions, it's quite feasible! As well as 1200 or 12000 transactions per day (40 transactions per block). In this case, would 30 light bulbs be a lot of energy compared to this number of transactions?

I'll let you answer that question on your own. :-)

<center><image src="../images/duniter-logo.png" width="200px"/></center>
