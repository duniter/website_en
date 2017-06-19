Title: Duniter version 1.3
Date: 2017-06-13
Category: Technique
Tags: release
Slug: duniter-version-1.3
Authors: cgeek
Thumbnail: /images/box.svg

Duniter version 1.3 is now [available for download](https://github.com/duniter/duniter/releases/tag/v1.3.8)!

## News

### Performances

The main characteristic of this new version is certainly the speed of the software to record new blocks: in version 1.2, the initial synchronization had become particularly long as the blockchain progressed. ARM nodes, often equipped with low-performance SD cards compared to conventional hard drives or SSDs, were particularly slow to process new blocks.

From now on, the reception of new blocks and the initial synchronization are up to 200 times faster than before!

As an indication, the initial synchronization takes less than 15 minutes to synchronize 26,000 blocks on a Raspberry PI 3. It could take [more than 2 days in version 1.2](https://forum.duniter.org/t/duniter-sur-yunohost-behind-a-box-type-privatrice livebox/2169/30).
 
### The arrival of modules!

It was a feature [announced during the RML9 at Le Havre] (/videos-rml9): Duniter 1.3 would connect modules on its own node!

As an example, it is now possible to add [the duniter-currency-monit plugin](https://github.com/duniter/duniter-currency-monit/releases) to its local node:

<img class="screenshot" src="../images/duniter-1.3/g1-monit.png"> </img>

A documentation of the modules is available on the [Wiki] (wiki/duniter/modules/).

### Cesium is no longer delivered by default

The Cesium client was historically delivered with Duniter. With the arrival of modules, this choice to install Cesium is left to everyone. The address of the Cesium module is:

    https://github.com/duniter/duniter-ui-cesium/archive/1.0.0.tar.gz

## Synchronization

> <span class="icon">![](../images/icons/white_check_mark.png)</span> No need to resynchronize. 

## Compatibility

> <span class="icon">![](../images/icons/white_check_mark.png)</span> Compatible with Ğ1.

-----

## Update version

* Link to [install the new version] (https://github.com/duniter/duniter/blob/master/doc/install-a-node.md) from a fresh workstation
* Link to [upgrade to the new version] (https://github.com/duniter/duniter/blob/master/doc/update-a-node.md) from an existing installation
