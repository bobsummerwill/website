---
layout: post
title: "About Hybris"
date: "2016-02-19 10:46:59 -0800"
permalink: /2016/02/19/about-hybris/
categories:
  - "Uncategorized"
---

![croppedimage608342-hubris1](/assets/images/croppedimage608342-hubris1.jpg)

**Want to run Linux on a mobile SoC?**

Well good luck with that, because you probably can't, due to the dominance of Android.

There just isn't a market for [X11](<http://x.org>) drivers, let alone [Wayland](<https://en.wikipedia.org/wiki/Wayland_\(display_server_protocol\)>) drivers, so most manufacturers won't even think about delivering SoCs which supports them.

Some options:

  1. Use Android. Obey your new masters. This is what most people do, if they even consider leaving "Apple world" in the first place.
  2. Use [AOSP](<https://source.android.com/>) (Android Open Source Project) on stock hardware, like a Nexus device. Except that AOSP is getting progressively crippled and abandoned, because Google's real operating system base is actually [Google Play Services](<https://en.wikipedia.org/wiki/Google_Play_Services>). Google really don't have your best interests in mind with Android. See [Google’s iron grip on Android: Controlling open source by any means necessary](<http://arstechnica.com/gadgets/2013/10/googles-iron-grip-on-android-controlling-open-source-by-any-means-necessary/>).
  3. [CyanogenMod](<http://www.cyanogenmod.org/>). Getting better. You've got yourself a usable OS, which some people actually prefer to commercial Android distributions. But you're still in much the same place.
  4. Use [Replicant](<http://www.replicant.us/>), which is built from CyanogenMed, but with every single bit of proprietary stuff removed. Better yet from a "freedom" perspective, but you are now really cutting off your own nose in regards to the hardware you can use. Replicant only works on [chronically old devices](<http://www.replicant.us/supported-devices.php>). And it still doesn't solve all the [privacy/security issues](<http://www.replicant.us/freedom-privacy-security-issues.php>).
  5. Opt out of Android entirely, and go for the only true mobile Linux which exists, [Tizen](<http://tizen.org>), which is actually running on X11. You can even buy real devices with it installed like the [Samsung Z3](<http://www.gsmarena.com/samsung_z3-7273.php>). But Tizen has [its own problems](<http://bobsummerwill.com/2015/07/26/tizen-the-emperor-has-no-clothes/>), the most acute of which, for potential end-users, is the complete dearth of available software, combined with no ability to run Android applications as a stop-gap, which makes the platform practically unusable, IMHO. Even Samsung struggle to get SoCs which support X11/Wayland. And Tizen 3.0, along with its open governance, has [still not arrived on commercial devices](<http://bobsummerwill.com/2015/09/16/tdc2015-tizen-3-0-first-milestone-what-does-that-mean/>).
  6. **None of the above? There must be a better way? Well ….**



 

The primary incompatibility between Android (which uses the Linux kernel) and existing Linux distros is the C runtime. For the Android user-land, Google chose to build [bionic](<https://en.wikipedia.org/wiki/Bionic_\(software\)>) (primarily to avoid GPL licensing), rendering Android applications binary-incompatible with Linux, even if they are running on the same hardware. Linux userland applications typical use the GNU C Library ([glibc](<https://en.wikipedia.org/wiki/GNU_C_Library>)).

This was the problem-space facing [Carsten Munk](<https://www.linkedin.com/in/carstenmunk>) in 2012, so he tried something crazy, and it worked. He built a compatibility layer for glibc sitting on top of bionic which allows both Android and Linux user-lands to co-exist on top of an Android kernel.

He later extended that model to GPU drivers, so you can run Wayland on top of Android drivers, which is a very neat trick.

Hybris is the "secret sauce" which lets [Sailfish OS](<https://sailfishos.org/>), [Ubuntu Phone](<http://www.ubuntu.com/phone>), [Plasma Mobile](<https://community.kde.org/Plasma/Mobile>) and [AsteroidOS](<http://asteroidos.org>) work on the mobile/wearable hardware which we actually have to work with right now. You can read more about it [on Wikipedia](<https://en.wikipedia.org/wiki/Hybris_\(software\)>) and check out the code [on Github](<https://github.com/libhybris>).

Hybris is the reason why the following fantastic devices coming to Mobile World Congress this year are possible:

  * [Meizu MX5 Pro Ubuntu Edition](<http://www.omgubuntu.co.uk/2016/02/meizu-pro-5-ubuntu-edition-specs-price?utm_source=slideshow>) smartphone
  * [BQ Aquarius M10 Tablet Ubuntu Edition](<http://www.pcworld.com/article/3025477/linux/bqs-ubuntu-tablet-could-showcase-long-awaited-desktop-mobile-convergence.html>), the first Ubuntu Convergence device
  * [Intex Aquafish](<https://en.wikipedia.org/wiki/Aqua_Fish>) smartphone
  * and why [AsteroidOS can run on an LG G Watch](<https://www.youtube.com/watch?v=b_GJiQYTAIk>)!



This magic opens up the possibility of Linux user-land in a world of Android-dominance.

We can all hope-and-dream of a future of open hardware and 100% open source drivers and bootloaders for them. In the meantime, Hybris lets those of us who cannot affect that situation continue to build freedom-respecting software in the real world.

Forever obsessing about things which are not under your control is not the path to happiness. Let's work on the pieces where we can make a difference **today**.

UPDATE: Also check out the [Open Devices project](<http://developer.sonymobile.com/2016/02/17/work-on-the-mainline-kernel-for-open-xperia-devices/>) from Sony which is working on a mainline Linux kernel for xperia devices.
