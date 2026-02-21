---
layout: post
title: "Possible stages for Windows open-sourcing"
date: "2015-07-26 22:36:31 -0700"
permalink: /2015/07/26/possible-stages-for-windows-open-sourcing/
---

_(first posted on[Engadget Public Access, 21st July 2015](http://www.engadget.com/2015/07/21/possible-stages-for-windows-open-sourcing/))_

A friend responded to my earlier [Will Microsoft open-source Windows?](http://www.engadget.com/2015/07/10/will-microsoft-open-source-windows/) article with the question along the lines of …

"**What about Enterprise customers? They won 't just leave that money on the table"**

And that is where we get into some subtleties, because we have always referred to **" Windows"** as something monolithic, but that monolith will have to be split apart in the process of open-sourcing, and then we are going to need some new words.

The simplest analogy, I think is to compare Windows to GNU/Linux, which is not a monolithic beast. We are going to have to start talking about Windows distros, and the Windows Kernel. In fact, that kernel is probably where the whole open-sourcing adventure is likely to begin, as I mentioned in the original article.

![](/assets/images/2016/06/build-marketecture-windows-8.png)

Both the **Windows for Devices** and **Windows Server 2016** possibilities I mentioned would actually probably start with open-sourcing of just the Windows kernel. I don't know whether those are separate code-bases, or how they are related, but they would probably be similar "shapes", and would likely be discrete "blocks" of code at the bottom of the stack which could be decoupled from any undesirable dependencies and "shipped". The Windows kernel is not an OS any more than the Linux kernel is a GNU/Linux distro, but it would be a start.

At that point, third parties could probably make their own "Windows distros", which would be a bit weird and not feel very "Windows-like". You could make command-line applications. You could maybe add Qt or similar and make a non-standard UI distro. It would be a start.

From there, Microsoft would need to start working their way up the stack. Even to reach **Windows Core** as I referred to in the earlier article might take quite a few steps. To be useful for porting existing Windows applications you would need the UI layer too. And then you are onto specific applications. Just as is the case for GNU/Linux distros and Android, there are lots of layers on the way up. That same journey would have to happen for Windows.

But I think the kernel is not necessarily such a big step. They just need to want to do it!
