Title: Duniter version 1.3.14
Date: 2017-07-05
Category: Technique
Tags: release
Slug: duniter-version-1.3.14
Authors: cgeek
Thumbnail: /images/box.svg

Duniter version 1.3.14 is now [available for download](https://github.com/duniter/duniter/releases/tag/v1.3.14)!

## Fixes

This version compiles the patches up to version 1.3.13, and brings a final touch to the Duniter network that had a tendency to fork regularly in recent weeks.

It seems that a bug in the IPv6 contact is causing the problem. IPv6 is now the last choice to contact a node, the order of preference is now: DNS, IPv4, IPv6.

This patch has been tested on a network node Ğ1, which immediately reveals nodes considered extinct for a long time from the point of view of this node, which considers them again *on and available*.

## Synchronization

> <span class="icon">![](../images/icons/white_check_mark.png)</span>No need to resynchronize.

## Compatibility

> <span class="icon">![](../images/icons/white_check_mark.png)</span> Compatible with Ğ1.

-----

## Update version

* Link to [install the new version](https://github.com/duniter/duniter/blob/master/doc/install-a-node.md) from a new server
* Link to [upgrade to the new version](https://github.com/duniter/duniter/blob/master/doc/update-a-node.md) from an existing installation
