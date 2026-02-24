---
layout: post
title: "#TDC2015 – Tizen 3.0 First Milestone – what does that mean?"
date: "2015-09-16 21:29:51 -0700"
permalink: /2015/09/16/tdc2015-tizen-3-0-first-milestone-what-does-that-mean/
---
![2015 05 03 09 06 14](/assets/images/2015/05/2015-05-03-09-06-14.jpg)



The **Tizen Developer Conference** is happening right now in Shenzhen, China.

[![tizen2015](/assets/images/2015/09/tizen2015.png)](/assets/images/2015/09/tizen2015.png)

Believe it or, this is actually the fourth annual Tizen Developer Conference:

  * [Tizen Developer Conference 2012 (San Francisco)](https://www.tizen.org/events/tizen-developer-conference/2012)
  * [Tizen Developer Conference 2013 (San Francisco)](https://www.tizen.org/events/tizen-developer-conference/2013) ([open governance](http://cdn.download.tizen.org/misc/media/conference2013/slides/TDC2013-Governance-Licensing.pdf) for Tizen 3.0 announced)
  * [Tizen Developer Conference 2014 (San Francisco)](https://www.tizen.org/events/tizen-developer-conference/2014) (I attended this one in my [MonoTizen](http://monotizen.com) days)
  * [Tizen Developer Conference 2015 (Shenzhen)](https://www.tizen.org/events/tizen-developer-conference/2015)



[Samsung Tomorrow](http://samsungtomorrow.com/) have just published [TDC 2015 Presents Tizen’s Future Roadmap in China](http://global.samsungtomorrow.com/tdc-2015-presents-tizens-future-roadmap-in-china/), giving an overview of the themes of the conference, but there is little else in the way of live coverage due to the [Great Firewall of China](https://en.wikipedia.org/wiki/Great_Firewall).

When that first conference was held in May 2012 (41 months ago), we were on **Android Ice Cream Sandwich** (4.0.x - API level 15) and**iOS 5**. The flagship phones in that month were the [iPhone 4s](http://www.gsmarena.com/apple_iphone_4s-4212.php) and the [Galaxy S III ](http://www.gsmarena.com/samsung_i9300_galaxy_s_iii-4238.php)(hot off the presses the same month). The first Tizen mobile device finally launched in January 2015, the [Samsung Z1](http://www.gsmarena.com/samsung_z1-6894.php), at a lower-spec than either of those flagships of 2012.

It looks like the pending [Samsung Z3](http://www.tizenexperts.com/2015/07/samsung-z3-device-given-to-attendees-at-the-tizen-developer-summit-2015-bengaluru-india/) phone will be roughly comparable to the Galaxy S III.

The Tizen Steering Group has just announced the first [Milestone Release for Tizen 3.0](https://source.tizen.org/release/tizen-3.0-milestones). Here are the talking points:

  * 2.4 public API (both Native API and Web API) is backward-compatible with 3.0 TV and Mobile profiles.
  * 64bit SoC is tested and verified with 3.0 TV and Mobile profiles.
  * 3.0 TV and Mobile profiles support multi-user architecture for multi-user/single-login usage.
  * New security architecture: 3 domain smack and Cynara
  * Security server and privilege manager are replaced with the new components, security manager and Cynara respectively.
  * X server is replaced with Wayland at this version.
  * Webkit2 is replaced with Chromium-efl and core components interacting with the web engine are re-designed/re-implemented for the new WRT and browser.
  * Buxton2 is introduced. Buxton2 provides secure configuration service based on Cynara and is re-implemented considering multi-user and recovery support.
  * Iotivity 0.9.2 is integrated into 3.0 TV and Mobile profiles.
  * Generic policy manager, murphy, is integrated into 3.0 platform.
  * Linux kernel 4.0 is provided.



So what does this really mean? Tizen 3.0 is "real"? Do we have open governance for Tizen Mobile, 28 months after it it was first announced? Have the [Emperor's clothes](https://bobsummerwill.wordpress.com/2015/07/26/tizen-the-emperor-has-no-clothes/) have arrived? Sadly not. 64-bit support is new and good, but …

What this announcement really means is the **Tizen 3.0** codebase (which had its first public milestone release [24 months ago](https://wiki.tizen.org/wiki/IVI/IVI_July_2,_3.0-M1)) finally has a Mobile profile which is feature complete. Crosswalk isn't finished yet, but it is feature complete. PS - "reference device for mobile profile is not available right now." That's right. There is no physical device in the world which you can get your hands on which runs this release. But it's feature complete. Even if you are one of the lucky few people in the world with the TM1 device given away earlier this year in India, you're still out of luck here. I imagine that TM1 will be supported soon. It has to be.

There is no IVI profile. Despite the fact that IVI is what the 3.0 codebase was built on, it has been silently dropped. We all [know why](https://bobsummerwill.wordpress.com/2015/07/26/tizen-the-emperor-has-no-clothes/), but let's move on to …

Wearable, which is the one profile which has had huge commercial success with Samsung Galaxy Gear, Samsung Gear 2, Samsung Gear Neo, Samsung Gear S, and the pending Gear S2. The Gear S2 has been the darling of the media recently, and rightly so. The last few Tizen 2.x SDKs have been moving towards a unified Mobile/Wearable delivery, so we're bound to have Tizen 3.0 Wearable, right? Wrong. No Wearable.

So IoT. Everyone is hot on IoT, right? Tizen - The OS of Everything. Tizen - The Best Way to Connect Everything. There will be proper IoT/SBC profiles in this release, right? We'll have an official IoT profile which works on the Raspberry Pi2, the Beagleboard and the Samsung Artik, right? It seems not. The Samsung Tomorrow article mentions "Micro Profile", but that again seems to be something which is planned, not current.

So what is new? A Tizen 3.0 TV profile which runs on an Odroid and a Mobile profile which doesn't run on any physical device which you can get your hands on.

Here is a summary of my understanding of physical devices which you can run the various Tizen releases on (any corrections I would love to hear):

Version | Mobile | Wearable | TV | IVI | Common/IoT  
---|---|---|---|---|---  
1.0 | [RD-210](http://www.tizenexperts.com/2012/05/hands-tizen-developer-prototype-device/) |  |  |  |   
2.0 | [RD-PQ](https://wiki.tizen.org/wiki/Reference_Device-PQ) |  |  |  |   
2.1 | [RD-PQ](https://wiki.tizen.org/wiki/Reference_Device-PQ) |  |  |  |   
2.2 | [RD-PQ](https://wiki.tizen.org/wiki/Reference_Device-PQ) |  |  |  |   
2.2.1 | [RD-PQ](https://wiki.tizen.org/wiki/Reference_Device-PQ) | [Gear 2](http://www.gsmarena.com/samsung_gear_s-6620.php) & co | [SmartTV 2015](http://www.samsungdforum.com/TizenIntroduction/) range? |  |   
3.0 IVI |  |  |  | Various | Various  
2.3.0 | [Samsung Z1](http://www.gsmarena.com/samsung_z1-6894.php) | [Gear S](http://www.gsmarena.com/samsung_gear_s-6620.php) |  |  |   
2.3.1 |  | [Gear S2](http://www.tizenexperts.com/2015/09/samsung-gear-s2-is-official-check-out-the-specs-and-the-voice-calling-features/) |  |  |   
2.4 | TM1  
[Samsung Z3](http://www.gsmarena.com/samsung_z3-7273.php)? |  |  |  |   
3.0 |  |  | Odroid XU3/XU4 |  | Various  
  
So what's new? Nothing which matters as far as I can see.

We still no concrete plans announced for any products to ship based on Tizen 3.0. The most important Tizen development (2.3.1 for Wearable and 2.4 for Mobile) is still happening behind closed doors at Samsung, and we don't even have Tizen 3.0 supported for the TM1 developer device which was given away at the Bengaluru summit earlier this year. It still has the flavor of R&D which _might_ lead to products.

[Developers, Developers, Developers](https://www.youtube.com/watch?v=8To-6VIJZRE) need **Devices, Devices, Devices**.

Please, please, please, Samsung, let's have _some_ development hardware and a competitive slate of Mobile products. Without those two key factors, you will continue to get a minimal amount of high-quality software developed for your platform. It is just too hard for developers to work, and is not worth their effort given the tiny market.
