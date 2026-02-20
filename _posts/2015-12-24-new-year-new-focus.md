---
layout: post
title: "New Year, New Focus"
date: "2015-12-24 13:08:32 -0800"
permalink: /2015/12/24/new-year-new-focus/
categories:
  - "Uncategorized"
featured_image: /assets/images/80163578_80163157.jpg
---

The New Year is going to see a new phase of development here at **doublethinkco**.

![80163578_80163157](/assets/images/80163578_80163157.jpg)

You're going to see a lot more hands-on work from this [old soldier](<https://www.linkedin.com/in/bobsummerwill>). I'm planning to finally get my hands dirty in the C++ code and start making concrete strides towards a [C++ Light Client](<doublethink.co/ethereum-light-client/>) after [our porting diversion](<http://doublethink.co/2015/09/22/porting-ethereum-to-mobile-linux/>).

[Anthony Cros](<https://github.com/anthony-cros>) has laid the foundations in the last few months. He has ground his way through lots of unglamorous build system work to give us the cross-build scripts inside [webthree-umbrella-cross](<http://github.com/doublethinkco/webthree-umbrella-cross>), and has got us working C++ cross-builds on:

  * Jolla Phone (Sailfish OS)
  * Meizu MX4 (Ubuntu Phone)
  * Raspberry Pi Zero, B and 2 (Raspbian)
  * Odroid XU3 (Ubuntu MATE)
  * Beagleboard Black (Debian)
  * Wandboard Quad (Debian)



Our flagship target device ([Gear S2 smartwatch](<http://www.samsung.com/global/galaxy/gear-s2/>)) is still fluttering just a fingertip beyond of our grasp, but it will happen soon, along with various other target devices - some rational (Android, iOS, Intel), some [whimsical (N900, N9)](<https://twitter.com/doublethink_co/status/680056050880389120>).

![20151020_063054](/assets/images/20151020_063054.jpg)

Anthony has [wrapped up](<http://doublethink.co/2015/12/22/wrapping-up/>) his contract for **doublethinkco** , and will be moving on to other projects. I would just like to take the opportunity to think him profoundly for everything he's done. I think it's fair to say that he have both learnt **a lot** in the process, and have equally high hopes for Ethereum.

So … it's just me for now, but that's fine. I've been a professional developer for nearly 20 years, with the vast majority of that on resource-constrained devices (games consoles) in C++. It will be a lot of fun.

I was only able to make occasional contributions in the past few months due to full-time work commitments at **TD Securities in Toronto** , where I met Anthony and many others in the Ethereum community. I'm back in Vancouver now and am working as a part-time contractor and consultant, so am able to leach a lot more of my own time into Ethereum work.

Pull requests for Light Client support have been [making](<https://github.com/ethereum/go-ethereum/pull/2005>) [their](<https://github.com/ethereum/go-ethereum/pull/2061>) [way](<https://github.com/ethereum/go-ethereum/pull/2019>) into the Go client. There is [more to do](<https://github.com/ethereum/go-ethereum/pull/2081>), but the LES/1 protocol is largely defined. LES/2 is starting to take shape.

It is time for somebody to grasp the nettle and start bringing C++ Light Client support to life, and it looks like I am the [itchiest person](<https://en.wikipedia.org/wiki/The_Cathedral_and_the_Bazaar>) 🙂

Best wishes to you all for the holiday season and New Year!

  * [Milestone 1 - Loose Ends, Tizen](<https://github.com/doublethinkco/webthree-umbrella-cross/milestones/Milestone%201%20-%20Loose%20ends,%20Tizen>)
  * [Milestone 2 - DevOps, Android, iOS](<https://github.com/doublethinkco/webthree-umbrella-cross/milestones/Milestone%202%20-%20DevOps,%20Android,%20iOS>)
  * [Milestone 3 - Light Client Phase 1](<https://github.com/doublethinkco/webthree-umbrella-cross/milestones/Milestone%203%20-%20Light%20Client%20Phase%201>)
