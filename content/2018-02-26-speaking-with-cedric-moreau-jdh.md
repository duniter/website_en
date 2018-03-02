Title: Speaking with Cédric Moreau, software developer of "libre" cryptocurrencies.
Date: 2018-02-26
Category: duniter
Tags: gitlab
Slug: cedric-moreau-duniter-protocol-inventor
Authors: thomasbromehead
Thumbnail: /images/logos/duniter.png


**Original french version by Carl Chenet (04/17), [read it here](https://blog.journalduhacker.net/index.php?article100/entretien-avec-cedric-moreau-createur-d-outils-pour-les-monnaies-libres) -**

####JDH: Hello Cédric, first and foremost I’d like to thank you for sparing some time for this interview with the Journal du hacker. Can you tell us who you are?

**Cédric :** Hello Carl, thanks for the interview. My name is Cédric Moreau aka **cgeek** on some forums. I’m 29 and an engineer in IT and automation. I live in Rennes with my girlfriend and my cat.
I started my career with 3 years as an employee in a tech company in which I was in charge of maintaining and later producing Java and JavaEE applications. In 2015, my third year there, I started working on my favorite language at the time, namely Javascript on Node.js.
I launched my own business **Art et Zerty** a year ago, in March 2016. I still work for some techs but feel more independent!
More interesting to you is that I started developing [Duniter](https://github.com/duniter/duniter) in the summer of 2013. It’s the world’s first software for producing "libre" decentralized cryptocurrencies and is libre -under GPL license, meaning the project cannot be privatized whereas open-source MIT projects can be), it goes without saying. I am the inventor and main developer to this day. It has been my life’s common thread for the last 4 years and will probably remain so for the rest it.

####JDH: Money seems to have made significant inroads into IT in the last few years. [Bitcoin](https://bitcoin.org) comes straight to mind as well as the whole cryptocurrency theme in general. Can you tell us what you mean by "libre" money and explain the use of Duniter?

**Cédric :** The "libre" money is a new concept, much like open-source in the eighties. Both concepts share a lot in fact since both put the user’s freedom as a core principle. Freedom to choose non-proprietary software for open-source and economic freedom in the case of "libre" money. 
Here are the 4 principles that make a "libre" money:

1. **Rule #1**: The user is free to choose his currency.
2. **Rule #2**: The user has free access to the monetary resources.
3. **Rule #3**: The user is free to decide what has value and what doesn’t.
4. **Rule #4**: The user is free to trade “in the money”.

Words have special weight here and I have to make them extra clear. The word "libre" for instance doesn’t mean “this that or the other” and so saying that the user has free access to the resources doesn’t mean that he could take them all and leave none to the others. Liberty here should be understood as "without detriment to my peers". Everyone has freedom of access to the resources but the same quantity and quality is available to others at any time.
The meaning of the 1st rule is that a currency chosen by one user cannot be imposed to everyone else.
In the same way, the logical trap of thinking that a "libre" money will **self-enforce** these rules is wrong. Don’t think for example that adopting a "libre" money would entitle you to rob your neighbour’s gold. 
A money can only be called "libre" if it **respects** these 4 guiding principles, in the sense that its monetary code doesn’t infringe them. The euro for example is not a "libre" currency because it has legal tender and is therefore imposed to citizens by a positive order. Bitcoin and gold are not "libre" either because production is in the hands of miners only, rules 3,4 and 5 are not observed.
Our "libre" money should be understood as applying the principles of the [Relative Theory of Money](https://en.trm.creationmonetaire.info/), the work of  fellow French engineer Stéphane Laborde and available under GPLv3 license. I suggest that everybody reads it, especially those who think a "libre" money is one that could be created by anyone. The RTM is our starting point.

So what’s the role of Duniter in all this ? It’s a software that enables the production of "libre" money. In terms of Object-Oriented Programming we can say that Duniter **implements** the "libre" money as defined by the RTM. 
 
####JDH: So if I’m right Duniter is the toolbox to launch A (and not THE) "libre" money ? I imagine that the launch of an actual "libre" money is your goal then? Where are you at with this?

**Cédric :** That’s right, A "libre" money because "libre" money doesn’t necessarily have to be digital nor need Duniter to work. A paper version could be created for example although it would be very costly to implement, both time-consuming and energy inefficient. In addition, IT tools would be needed at some point to make sure no one is stamping excess money or distributing too many Universal Dividends and/or of incorrect amounts.
Starting out with a digital implementation is much smarter especially if you want the community to grow fast. It makes it so much easier to verify that no-one has a double identity which would grant him or her twice the amount of Universal Dividends. This verification is done through a Web of Trust (WoT). 
Our Web of Trust is specific to Duniter, it is not a built-in feature of the "libre" money. It just so happens that "libre" money requires each member to have a verified identity for the minting of the UD which is why we need it. It could probably also work with other technical solutions.
So let me go back to your question of where we stand right now. I’m very proud to say that after 3 ½ years of development, we launched the very first "libre" money powered by Duniter on the 8th of March 2017 at 4:32PM. Codename: Ğ1. It was officially announced on the [duniter.org](https://duniter.org/en/) website.
As of today (April 13th, 2017), the Ğ1 has been adopted by 73 users and has a supply of 18 220 units. Being a "libre" money this value increases daily because all member co-produce their fraction of it. Today at around 1PM I myself  will produce 10 Ğ1 credited to my personal wallet. Just like everyone else who’s a member of the WoT.
 
####JDH: When I think of a particular cryptocurrency, I instantly think of its use cases and its main purpose, often decided by the creators and first users. What’s the purpose of the Ğ1? What are actual use cases our readers could relate to and where do you see it going?
 
**Cédric :** We’re only at the beginning obviously but the currency doesn’t seem to be used much as a medium of exchange yet. The community needs to grow so that more products and services become available but some are starting to accept it as payment. There’s a restaurant in Nantes called the [Etrillum](https://forum.duniter.org/t/etrillum-restaurant-en-monnaie-libre-g1/2145) where you can pay in Ğ1, the café at the last Rencontre de la Monnaie Libre 9 (Libre Money Meetup) or a carpool ride to the event were payable in Ğ1 as well. 
Most of the transactions we are seeing on the blockchain are donations, mostly to those running a Duniter node, to the developers working both on Duniter and its clients (Sakia, Cesium, Silkaj) and in a broader sense to all those involved with the Ğ1 in one way or another. I’m not constantly keeping an eye on transactions so there must be many I’m unaware of!
A marketplace will soon be launched (now available) offering goods and services payable in Ğ1. It’s called ğchange and was created by kimamila, the person also behind Cesium. Ğchange (pronounced the same way as “I exchange” in French) will be available as a website (it is, see here) and will be built with either Mastodon or Diaspora-like pods. I think it is the one thing we need to make the next big step forward. Ğchange runs on ElasticSearch nodes and the front-end is based on Ionic2. Any help is more than welcome! 
In the meantime we are actively seeking new members to join us so that they can benefit from this hatching economy and certify new members. To give you an idea, we are currently 73 vetted members and we have around 300 members waiting for their 5 certifications. There’s a long road ahead of us!

####JDH: You mentionned Sakia, Cesium and Silkaj. You explained Duniter to us but can you break down what these clients do?

**Cédric :** If Duniter is the heart of the network [Sakia](https://github.com/duniter/sakia), [Cesium](https://github.com/duniter/cesium) and [Silkaj](https://github.com/duniter/silkaj) are satellite utilities that connect to it. We use the word client for them. Why do we need clients? Because not every single user needs to have Duniter running on his/her computer, which would require it to be online 24/7, have a full copy of the blockchain and verify its current state to generate new blocks. Clients are tools that communicate with Duniter (the heart) to make operations such as send and receive transactions, join Ğ1 as a member or certify your peers.
 
Sakia was the very first client, written in python. It’s a desktop application that can run on most Linux distros. All operations that can be carried out on the Ğ1 network can be done via Sakia (transactions, WoT) while also enabling basic network monitoring (supply, blocks etc).
Cesium is Sakia on the web. It does what Sakia does but on your browser. It’s also reputed to have a friendlier learning curve for non-techies since it requires no setup. 
Silkaj is the latest kid on the block. It’s an online command line interface whose main function until now was to explore the network and see a few technical details. Its capabilities were recently extended to manage transactions. You can now exchange money over the command line, which can be very useful for setting up recurring payments or other automated tasks.

####JDH: That’s terrific, I see the project is really gaining traction. What use do you see for the Ğ1 and what’s its role in society in your wildest dreams?

**Cédric :** In my wildest dreams there’s a million of us in the WoT. Quite a small number when you think of it, 1 in 67 French. To think that a million users are creating their own money every day and are deciding what has value instead of the banker is truly exciting. What if 10% of them are developing libre software? What an amazing springboard to innovation that would be! Think of so many other value drivers currently stifled by innovation limited to the bounds of banks’ walled gardens.

I can’t foresee what use humans would make of a "libre" money because I don’t know what they want to do with it in the end. We each have our opinion on the question and that’s the very essence of a "libre" money; to make us realize that we’re not in any position to say what "production" is or isn’t because that’s making a relative statement, not an objective one. I view open-source as offering so much more than proprietary solutions. Not everyone agrees on that of course. So what happens when you cut the leash and let humans indulge some of their time in creating the values that they themselves consider to be "production", where would that take us? 
Playing Ğeconomicus offers a glimpse into that. It lets players simulate a "libre" money ecosystem over a timeframe of 80 years, the average lifespan in Europe. I won’t spill out the beans here, I’d rather let those interested search for the results online or even play it themselves. All I’ll tell you is that playing is really eye-opening and I love the new horizon it offers us.
With only 73 members (now XXX) we still have a long way to go. But then again there were only 59 of us a month ago, so that’s a 23% growth. If it went on like this for three years we could reach the same number of wallets that bitcoin took 5 years to reach. I’m an optimist and like to think that we’ll get there. To the Moon!

**JDH :** Thank you Cédric for this interview.

