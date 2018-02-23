Title: Duniter, why and how ?
Date: 2018-02-23
Category: duniter
Tags: gitlab
Slug: duniter-why-how
Authors: inso
Thumbnail: /images/logos/duniter.png

Last year (2017) will go in history as the first year of production of the ğ1 currency. 
A milestone to be remembered as the community’s efforts had until then been almost entirely devoted to launching production of the world’s first 100% P2P “freedom-enabling” cryptocurrency. Looking back at 2017, we have grown from the initial 59 members to well over 600 as of early January of 2018. Local ğ1 networks have sprouted across France and in nearby French-speaking countries and the project is gathering growing attention and gaining momentum

Here’s an example conversation we heard repeatedly in the last year.

> - “What’s this Duniter cryptocurrency all about?”  
- “What’s this Duniter cryptocurrency all about?”  
- “Wow that sounds very interesting! But how does it work then? How does it fight off Sybil attacks? How does the blockchain work? How hard is it to become a member?

In twenty eighteen we’ll be going into depth on the project and on how Duniter works. We’ll kick off with a series of 12 articles which we hope will give everyone a better understanding of the Duniter protocol and its intricacies.


# A "libre" currency?  ?

Duniter’s goal is to create money following the principles of the Relative Theory of Money in which the currency is “minted” by way of a Universal Dividend (UD or DU for Dividende Universel in French). Because each vetted member is a co-creator, the money offers symmetry for all: whatever the age and whether alive or not. Each individual (companies do not create the ğ1 but can participate in the network) co-creates the same percentage of the total money supply in a given timeframe (40 years with the ğ1):

- Money being co-created by every vetted member, it can be seen as **a universal income emerging from the creation of the currency itself.** Think of mining fees and mining rewards evenly distributed to each holder of a bitcoin wallet.
- Money creation grants no privileges to some at the detriment of others, at any given time t or over larger periods of time.
- The co-creation allows us to measure exchanges between individuals with an unbiased meter and therefore becomes **a common yardstick** in the true sense of the word. 

The Universal Dividend gives the ğ1 some unique characteristics:

- **Money from the deceased is constantly replaced by money from the living.** The money is constantly "circulating" at the expense of no-one.
-The money supply slowly reaches a cap of around 3800 UDs (in the ğ1) over the course of a member’s life. 

We’ll go into greater detail on this in the next articles.


# A “Web of Trust”?

In order to clearly identify each member and ensure that no-one receives two or more UDs we resorted to a WoT. We borrowed the term from [PGP](https://fr.wikipedia.org/wiki/Pretty_Good_Privacy), the famous open-source encryption software although our implementation is vastly different. The WoT is there to make sure a **real-world identity matches that on the network.**

The WoT is woven by members themselves. The 59 "founding fathers" asserted that they knew each other in person and each then proceeded with “certifying” others around them. When a new member joins, he or she is given the right to certify future members. 

However the process **can’t go on forever** as the web has a maximum diameter. Each member only has a set number of certifications he can grant and cannot be “too far” from other members. If you’re interested in the fine print, I invite you to read this article from 2016 called “[Introduction to member management](https://duniter.org/fr/introduction-a-la-toile-de-confiance/)” .


> *The WoT is the aggregate of all links between human beings. I know someone who knows someone. Legend has it that we are only 5 levels from each other.*  
-- [@paidge](https://www.youtube.com/watch?v=coFgDw2yH0g)  --

# A blockchain without “mining”?

Duniter’s blockchain moves forward thanks to the nodes provided by members. These nodes **calculate new valid blocks** but there is **no mining** involved here as the ğ1 is created by the Universal Dividend! 

Whether a member’s node is active or a mirror, **it always contributes to the co-creation of the money**. Members are invited to run a node if only to strengthen the blockchain and make sure that exchanges do happen. 

To help distribute the cost of running nodes across all members a redistribution [service](https://remuniter.cgeek.fr/) was created. It works on a voluntary basis whereby members make a small donation which is then split between all nodes working on blocks at the given time. Bear in mind we are talking about money that already exists here. This service is not part of the heart of the money creation itself. 

The more members contributing in hash power the sturdier the blockchain (less likely to be compromised).  The software must be as cost-efficient as possible to keep calculating costs at a minimum. We’ve therefore opted for a **personalized difficulty** tailored to each member. In practice this means that a member with a potent computer is slowed down so that even a Raspberry PI will be able to generate blocs in the future. We’ll cover this better in a coming article!
                                   
# We’re done with the basics 

As you’ll have gathered, Duniter’s main difference is that **it puts humans first**.
The money creation is taken care of by humans themselves, not by machines or private corporations. Humans meet and validate each other’s capacity to create the money. 

In the best of worlds each member would have a calculating node giving each and everyone a say in the growth of the network and in future decisions. 

To avoid confusion between the protocol and the currency, we’ve distinguished the two, the former being Duniter and the latter the **ğ1**. **Tech and economics are two very different subject matters!** 

Duniter (DU – unit – er) is a way of saying "Machine calculating UDs". The software allows the instantiation of a currency, in our case the ğ1. It allows humans having confirmed knowing each other through the WoT and the blockchain to calculate the UDs for the community and… greater good! 

**Is is indeed the mere action of validating your peers’ real-life identities and of running nodes that are the source of the money creation.** 

# Coming soon...

We hope you’ll enjoy the upcoming articles which will allow you to get better acquainted with the technology.  

>*“A currency is something that embodies value, can be exchanged on the basis of its >value, and can be transferred from place to place. In the world economy, the currency is >money, not a thing of value in itself but a carrier of value, a surrogate of value. >Finally, the currency must be fluid –easily flowing from place to place or situation to >situation- in order to bind the ecology together. It is what makes the ecology a single >system rather than a mere aggregation. If currency is hoarded, it is unproductive and >does nothing to increase the overall value of the ecology. In a balanced ecology, nothing >is wasted. Each actor has an essential freedom of action, and so is free to discover and >exploit locally available resources that would have been overlooked and thus wasted by a >system that relied upon centralized control. If you’re not fast you become food. And >there’s no begrudging the discarded waste that somebody else finds useful.”*
Mickey McManus, [Trillions: Thriving in the Emerging Information Ecology](http://trillions.maya.com/), 25/09/2012.
