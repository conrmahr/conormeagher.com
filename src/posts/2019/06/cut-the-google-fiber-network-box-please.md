---
templateEngineOverride: njk,md
metaTitle: Cut the Google Fiber Network Box Please 
metaDescription: Cut the Google Fiber Network Box Please
title: Cut the Google Fiber Network Box Please 
description: Now you can bypass the Network Box and plug directly into your own hardware
featuredImg: wan-network
subHeading: Now you can bypass the Network Box and plug directly into your own hardware
tags: [ "Advice", "Google Fiber", "Internet", "Networking", "TV"]
date: 2019-06-08T23:00:00Z
updated:
published: true
---

<div class="col-start-3 col-end-9">

With my consecutive [Cut the Cord Please](/posts/2018/01/cut-the-cord-please/) and [Cut the Cord Please, Again](/posts/2018/06/cut-the-cord-please-again/), its now about cutting the hardware. The Google Fiber Network Box is not the most hi-tech piece of equipment. A low-end 802.11ac radio, cloud-only admin login, limited networking options, but worst of all, no Bridge-Mode! Advanced users are not going to use this box while routing 1 Gbit/s of bandwidth throughout their home or office. Use your own Wi-Fi router?[^1]

> Google Fiber recommends you to Double-NAT it. Yuck.

How about tagging it to VLAN2? Yes sir. Now you can bypass the Network Box and plug directly into your own hardware. Here's how to do it with a [Ubiquiti Unifi Security Gateway (USG)](https://amzn.to/2Mwa5pN):

### Ubiquiti UniFi

- Plug the Fiber Jack directly in the USG WAN port
- Power the Fiber Jack with plugging in the USB power adapter.
- Login to the UniFi controller
- Go to Settings > Networks > WAN > Edit
- Toggle Use VLAN to on
- Set VLAN ID to 2 and QoS Tag to 3
- Click Apply Changes

### No VLAN Tagging

There has been user reports that Google Fiber is getting rid of the VLAN tagging requirement.[^2] That has not been the case for me in the Kansas City metro area but it's important to note that I use the GFLT110 compared to the newer GFLT300 model Fiber Jack.[^3] Maybe it's model specific or just Fiber City specific.

https://twitter.com/conrmahr/status/1137258538336772096

[^1]: ["Google Fiber Help: Use your own Wi-Fi router"](https://support.google.com/fiber/answer/2446100). Retrieved June 8, 2019.
[^2]: ["r/googlefiber VLAN"](https://www.reddit.com/r/googlefiber/comments/9do9s3/vlan/). Retrieved September 2018.
[^3]: ["Google Fiber Help: About your Fiber Jack"](https://support.google.com/fiber/answer/2667494). Retrieved June 8, 2019.

</div>