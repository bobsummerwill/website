---
layout: post
title: "Will Microsoft open-source Windows?"
date: "2015-07-10 01:18:44 -0700"
permalink: /2015/07/10/will-microsoft-open-source-windows/
---

![](/assets/images/external/misc/Windows_8.1_Start_screen.jpg)

My spidey-sense is telling me that Microsoft are going to open-source Windows within the next 12-24 months. That would be quite the pivot, wouldn't it? But I think that is how things will pan out.

Why would that make any sense? Isn't Windows the crown-jewel of Microsoft? Hasn't it been their primary cash-cow for decades? What are you smoking, Bob? Why on earth would they do they?

The world has changed since the 90s, and Microsoft have really changed as a company in the last few years, as [Scott Hanselman](http://www.hanselman.com/) expressed so well in his [Microsoft Killed My Pappy](http://www.hanselman.com/blog/MicrosoftKilledMyPappy.aspx) article. It is very apparent in the actions which Microsoft have taken in the last couple of years that they recognize that only providing Microsoft software and services on Windows makes no sense anymore. Back when Windows PCs were the only game in town, that kind of coercive bundling made business sense, though it was never a very "nice" approach. With the shift of eyeballs and fingertips from Desktop to Tablets, Mobile and Web, companies who want to have any commercial success need their software and services to be available everywhere. If you aren't on Android, iOS and the web then you are dead in the water.

Microsoft's future business will all be focused around Azure, and Office 365, and Visual Studio Online, and similar services. Use our data centers. Use our SaaS offerings. From whatever local device or OS you like.

Does that mean that Windows is dead? Far from it. For Desktop and business scenarios, Windows is still very dominant. OSX is increasing finding its way into businesses too, but Windows will be around for decades to come. The overall trend, though, is for operating systems to become commodity goods. Nobody wants to pay for them. They're only there because you need them, not because you want them particularly. For many people's daily use-cases OSes only really exist as containers for browsers and apps. You don't really "do much" in the OS itself. It's just the "thing with the global settings dialog".

Microsoft are embracing Linux, and embracing iOS and Android. They have to. So where does that leave Windows? It becomes just another path into the Microsoft software and services eco-system. Nobody wants to pay for the OS. So Microsoft [aren't really charging any money for Windows 10](http://www.forbes.com/sites/gordonkelly/2015/06/17/windows-10-free-for-1-year-what-happens-next/). That is not the same as being open-source, of course.

What might the path to open-sourcing for Windows look like? Much like the pattern for .NET open-sourcing, I think. Why did Microsoft open-source .NET? For much the same reason as they would open-source Windows - that the "layer" had become a commodity, and so open-source, community-friendly development just made better sense.

In the same way that .NET Framework is a hairy beast, I'm sure the innards of Windows are even more scary and messy, and unsuitable for a straight "code drop". In the build system and supporting tools there will no doubt be references and dependencies onto numerous Microsoft internal systems which would not be "coming out" of Microsoft at the same time. So what do you do? You do it incrementally, and release some more manageable subset, and then you grow it from there. Just like the .NET Core approach.

What might that "core" be for Windows? I think that there are two obvious candidates:

  * Windows for Devices
  * Windows Server 16 "Pico"



Both of these profiles will be small and more manageable. They don't have an UI layer. They're just focussed on processes and threads and drivers and so on. They would be analogous to the Linux Kernel in footprint. Well, there will be a bit more than that in the releases, but they are tractable at least.

And perhaps an approach directly analogous to .NET Core is possible for the OS as well? That would be to rebuild the higher layers on top of that open-source core in a "packages" style way. You switch all the higher-level parts of the OS to be delivered as components through the Windows Store. That probably isn't possible for things as fundamental as "The UI", so maybe you're looking at level two of that open-sourced solution being "Windows Core + UI".

The [recent changes](http://www.theverge.com/2015/7/8/8913365/microsoft-lumia-windows-phones-strategy-2015) in the Microsoft phone business also point in the same direction. Without Windows becoming a commodity product, Windows phones don't have much sparkle. Why would you buy a Windows phone when all the software ecosystem and network effect is happening in Android and iOS? Microsoft recognized that in [offering a path for iOS and Android apps to come to Windows 10](http://www.engadget.com/2015/04/29/android-ios-apps-on-windows-10/). At that point, Windows for Phones becomes more analogous to Google Nexus. A reference/research platform which might sell a few devices, and which is worth keeping around, but which is NOT a primary pillar of your business.

So in the coming 12-24 months we would have the following open-sourcing initiatives …

  * Windows Core (first for IoT, later for Server 2016 Pico)
  * Windows Core + UI (first for Phone and Tablet, later for Desktop)



Seeing an open-source Windows covering all profiles maybe by the end of 2016, or perhaps early-to-mid 2017.

A per this Wired artlcle, [open sourcing is no longer optional, even for Apple](http://www.wired.com/2015/06/open-sourcing-no-longer-optional-not-even-apple/). Even for Microsoft. Even for Windows.

Or not! We will find out soon enough.
