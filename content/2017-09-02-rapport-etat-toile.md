Title: Ğ1 Web of Trust report (September 2 of 2017)
Date: 2017-09-02
Category: Web of trust
Tags: wot
Slug: report-state-wot
Authors: elois
Thumbnail: /images/network.svg

Since [4 July 2017](https://forum.duniter.org/t/currency-monit-monitoring-dune-monnaie- and-sa-toile-de-confiance/2770/17?u=elois) I keep detailed statistics on the status of the web of trust that you can view on [g1-monit.elois.org](https://g1-monit.elois.org).
* These statistics are produced by `duniter-currency-monit` (duniter-currency-monit`), which is used directly in the local block of the duniter node. which it is installed. *

I decided to take advantage of these statistics to publish regularly a short report on the global state of the web of trust Ğ1.

## The spirit of these short regular reports

The objective of these short regular reports is not to be exhaustive, but rather to highlight certain indicators that seem relevant at a given moment to visualize a given phenomenon. There is no defined frequency, I will publish a report whenever there seems to be something relevant to describe and that I will have time for.
If you regularly read my reports, which you regularly read *g1-monit* and you want to write reports, you can [contact me](https://librelois.fr/contact/) to be discussed :)

# Prerequisites
Before reading these reports, it is strongly recommended that you review the [license Ğ1](https://duniter.org/en/files/licence_g1.txt) and read all the following pages:

* [Become a member of the Ğ1 web of trust](https://duniter.org/en/wiki/devenir-membre)
* [Certify new members](https://duniter.org/en/wiki/certify-of-new-members)
* [Frequently Asked Questions on the web of trust](https://duniter.org/en/faq/)
* [**How the web of trust works**](https://duniter.org/fr/introduction-a-confiance_silver/)

In particular, reading the article [**Introduction to the web of trust**](https://duniter.org/fr/introduction-a-confiance-style/) is essential to know the function of each of the rules of the web.

I will also use notions of graph theory, but I will try to define each time the terms used.

Finally, you must know a specific scale to the duniter web of trust, **the quality of a member**.

## Quality of a member
What I call quality of a member is the ratio between the rate of referring members that can be achieved by a certification of that member and the rate of referring members that must be reached in order to respect the rule of distance.

I will give an example to make it clearer: let's take a web of trust with 10 referring members and xpercent = 0.8.
The quality of a member in such a web of trust is the ratio of the number of referring members that it allows to join in less than 5 steps (numerator) on the number 8 (denominator).
So if a member Bob allows to join 4 referents it will have a quality of 0.5.
And if Bob allows to join 10 referents it will have a quality of 10/8 = 1.25.

What do I mean by "join"? When I say that Bob allows to join x referring members I hear that if Bob certifies a new identity (which is only certified by Bob) then there will be x referring members for which there will exist a path of less than 5 steps towards the new identity.

Thus, a member with a quality greater than or equal to 1 could let in a new member by itself if the sigQty rule did not exist.

When the average quality is greater than 1, the distance rule is not limiting. When the average quality approaches 1, the rule of distance will become limiting for some minority cases. And when the average quality becomes less than 1, then the rule of distance becomes limiting for the majority of identities (by identities I mean new members but also members wishing to renew!)

Currently the average quality is **1.04**, which means that the rule of distance is not limiting, so the web of trust is not "too tight". 1.04 is close to 1, so if all the members only certify outwards from now on the rule of distance could become limiting quickly (which may be a desirable and desired situation in some cases, it is also a freedom of the members to tend or relax the web of trust).

# Ğ1 Web of Trust report (September 2 of 2017)

## Observations

We are two weeks after the passage of the level Y[n]=4, here is a reminder of the effect that this level had had:

> The quality of the web of trust will increase slightly after this stage, approximately 88% of members will have a quality >= 1 against 83.75% currently. A gain of 4%. The rule of distance will therefore be globally less constraining but not of much, and at the current rate of growth of the number of members, the web will quickly stretch again! The number of referents will increase from 150 to 140, which shows that the members do not stop with 3 certifications issued, they continue to issue.

The densification effect of the level has already dissipated, the web of trust is again as taut as before the passage of the level, or even slightly more:

* The proportion of members with a quality >= 1 fell to **82%** about the same level as before the level (83%).
* In addition, a dozen members begin to fall to very low quality levels (less than 0.9), which means that they start to be too far from the referring members, black areas on this graph on page [web of trust quality] (https://g1-monit.elois.org/gaussianWotQuality?lg=en): </BR><img src="https://librelois.fr/public/qualite-toile-020917.png" width="690" height="339">
* Moreover, of the 79 future members who have received at least 1 certification, 7 of them do not respect the rule of distance, 3 have been certified by the same member. Nevertheless these are  **4 different cases of non-compliance with distance rule**.
* Another indicator shows the tension of the web of trust, **the increase in the average length of the shortest path between two members** which is now **4.13**. This value has increased continuously even when passing the level because it is independent of the notion of referent member. It shows the state of tension of the entire web of trust where the quality  of a member only shows the state of tension of a subset of the web (the subset of referent -> member links).
* Lastly, the number of referring members has risen above its pre-stage value (153):
<img src="https://librelois.fr/public/fin-effet-palier-yn-4.png" width="690" height="339">

## Interpretations

The rule of distance is still very far from being blocking, but the web has never been so tense since I keep very detailed statistics on its state, that is to say since July 4, 2017.

The Ğ1 web of trust is becoming tense because the flow of new entrants goes faster than the internal recognition between the members already members. This phenomenon is perfectly normal at the beginning of currency and will accelerate as the Ğ1 will gain in popularity. The web of trust will therefore most likely continue to tighten until the distance rule becomes blocking.

At that point, the new entry flow will slow down and the members who were then very active outward will have to certify inward to densify a bit the web so that it can again welcome.
Again this is a normal phenomenon at the beginning of the currency and even desirable because this constraint on the inputs will also limit the possible sybil micro-attacks in progress (the small frauds) so that they remain microscopic with respect to the size of the canvas.

* Aparté: I remind you that it is impossible to prevent small frauds, there will necessarily, perhaps even already, the only thing one can and must do is to constrain these small frauds to remain marginal so that the globality of the web remains trustable and it is precisely the role of the rule of distance.

This is why it is important to insist that the other members of the Ğ1 you meet on the fact that they must certify the members they know personally even if they are already members and must do so without waiting.
This point is not always well explained and even less understood, and it is understandable given the quantity of new concepts to be integrated elsewhere. If we do not insist sufficiently on the importance of internal certifications then there may be many misunderstandings when the rule of distance becomes blocking, and this misunderstanding could cause mistrust and inhibit the popularity of Ğ1.

It is necessary to qualify this global statement by specifying that the web is regionalized, so the rule of distance will become limiting only in certain regions and not at all in others. To anticipate that, it is enough to monitor members with the weakest quality, and if it starts to concentrate a lot in the same area, we can very well directly contact local groups in this area, and by the same occassion teach them to use g1-monit to monitor their own situation in the future.

## Conclusion

The various indicators of the state of tension of the web of trust will allow us to anticipate, and that is the whole objective of the development of g1-monit and the writing of these reports: awaken your vigilance so that you watch - even your web of trust, after all it is a common good :)

Some people are of the opinion that the distance rule is too restrictive and will have to be relaxed, other than the current rules are perfectly suited and that members of the Ğ1 are able to regulate their own balance between their internal and external certifications. Will the members of the Ğ1 be vigilant enough to regulate the web of themselves? I hope the answer is yes, tracking detailed statistics of the web will tell us :)
