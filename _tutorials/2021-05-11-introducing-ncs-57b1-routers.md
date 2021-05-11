---
published: false
date: '2021-05-11 22:04 +0200'
title: Introducing NCS 57B1 Routers
author: Nicolas Fevrier
excerpt: Introduction of the new NCS 57B1 Routeurs
position: hidden
---
{% include toc icon="table" title="NCS 57B1 Routers" %} 

## Intro

With IOS XR 7.3.1, we introduced multiple software features ([https://xrdocs.io/ncs5500/tutorials/iosxr-731-innovations/](https://xrdocs.io/ncs5500/tutorials/iosxr-731-innovations/)) but new hardware. Among them, the NCS 57B1 series.

These two new routers are the NCS57B1-6D24 and NCS57B1-5DSE, both  1RU systems with a mix of 100G and 400G ports and powered by a Broadcom Jericho2 NPU.

## Videos

<iframe class="responsive" width="560" height="315" src="https://www.youtube.com/embed/MyqmIlozL8M" frameborder="0" allowfullscreen></iframe>{: .align-center}
.

And since you didn't ask for it, the unboxing :))

<iframe class="responsive" width="560" height="315" src="https://www.youtube.com/embed/HRKhKuMAy-g" frameborder="0" allowfullscreen></iframe>{: .align-center}
.

## Product description

You can find the datasheet on Cisco's website:  
[https://www.cisco.com/c/en/us/products/collateral/routers/network-convergence-system-5500-series/datasheet-c78-744698.html](https://www.cisco.com/c/en/us/products/collateral/routers/network-convergence-system-5500-series/datasheet-c78-744698.html)

We differentiate the:  
- base system (Jericho 2 without eTCAM) offering 24x 100G and 6x 400G ports: NCS57B1-6D24
- scale system (Jericho 2 with OP2 eTCAM) offering 24x 100G and 5x 400G ports: NCS57B1-5DSE

The difference between the two versions is simply the presence of an eTCAM and for the system equipped with this additional resource, we have one port QSFP-DD 400G left.  
The connection to the eTCAM is made through fabric ports for the routes and classifiers, but we are using "NIF" ports for the statistics, hence the impact on the 400G port density.



### NPU

These routers are "system on a chip" or SoC. All ports are connected to a single chipset (via reverse gear boxes, we will describe it further, later with the block diagram). That makes the design very simple and efficient in term of latency, performance and power consumption.  
At the heart, we have the Broadcom Jericho 2 NPU. It offers 4.8 Tbps and 2BPPS of forwarding capacity. 




----

<div class="highlighter-rouge">
<pre class="highlight">
<code> "Pre-existing [hw-module fib ipv4 scale internet-optimized] config has "  
 "been found. This feature isn't supported anymore and therefore ignored. "  
 "Please delete this config. "  </code>
</pre>
</div>

![host-optimized-default.png]({{site.baseurl}}/images/host-optimized-default.png){: .align-center}
