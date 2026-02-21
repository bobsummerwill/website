---
layout: post
title: "First steps on the path to Tizen self-hosting"
date: "2014-08-11 03:44:11 -0700"
permalink: /2014/08/11/first-steps-on-the-path-to-tizen-self-hosting/
---

Before I attended the Tizen Developer Conference in San Francisco in June 2014, I already had a strong sense that Linux host machines were hugely important for Tizen development, where iOS and Android development have been primarily Windows and Mac-oriented. On the first night of the conference, though, I met [Rasterman](http://en.wikipedia.org/wiki/Carsten_Haitzler) who put me on the track to a braver goal - aiming to self-host on Tizen.

With the release of [MonoTizen-1.0.0](http://monotizen.com) in July 2014, we already have Linux-hosted C# development for Tizen. The next steps on this path is getting that [Mono Runtime](http://www.mono-project.com/Mono:Runtime) incorporated into the Tizen distribution as [community supported code](https://wiki.tizen.org/wiki/Community_supported_code) and then getting that [MonoDevelop IDE](http://monodevelop.com) migrated over from a Linux host onto the Tizen device itself.

Is that going to be lots of work? Not so much. We didn't bother getting libgdiplus onto Tizen. That shouldn't be hard. The slightly larger chunk of work is getting [GTK+](http://www.gtk.org/) in, so that [Gtk#](http://www.mono-project.com/GtkSharp), the basis for the [MonoDevelop](http://monodevelop.com) UI can be used on Tizen device. I think that's going to be about it, though that might not look pretty, or be very usable. That's our starting point, though, and I don't think that is very far away.

In the meantime, I tried out Bluetooth keyboard and mouse and MHL output on my Samsung Galaxy S4 to get some idea of what this self-hosting setup might feel like on a Tizen device like the Samsung Z:

And I also tried out the Bluetooth keyboard against the RD-PQ, to see whether that would "just work". It did.

The Bluetooth mouse did not work, and I know that MHL is also not functional on the RD-PQ, though I understand that it will work for the final Samsung Z hardware.

My dream scenario, which might take a few years to achieve, is to use a wearable as all of the computing power you need, with wireless input and wireless audio and video output.

There is a [Bluetooth Video Profile](https://developer.bluetooth.org/TechnologyOverview/Pages/VDP.aspx) but it looks like it is not broadly supported yet. The [BlueZ](http://www.bluez.org/) Bluetooth stack used in the Linux kernel and in Tizen appears not to support VDP yet, though there are references to at least two Google Summer of Code projects to try to add that support.

Perhaps more will be possible on the Tizen wearable profile if the [Gear Solo is announced as expected](http://www.tizenexperts.com/2014/08/samsung-to-launch-gear-solo-sm-r710-at-ifa-2014/) in September 2014.
