---
layout: post
title: "EASTL has been open-sourced by EA.   For real!"
date: "2016-02-10 00:27:01 -0800"
permalink: /2016/02/10/eastl-has-been-open-sourced-by-ea-for-real/
---

I am delighted to see that EA have finally open-sourced EASTL **for real** , after a very convoluted journey starting in 2007.

You can check it out [on Github](https://github.com/electronicarts/EASTL), and build it yourself using [CMake](https://cmake.org/).

![ea](/assets/images/2016/02/ea.png)

**What is EASTL, you may ask?**

It is a variant of the standard C++ STL (Standard Template Library) which is optimized for the specific needs of videogames software. [Paul Pedriana](https://www.linkedin.com/in/paul-pedriana-3ba1bb2), its creator, wrote [an article about it back in 2007](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2007/n2271.html), but no code was released at the time.

EASTL is a foundation technology for all of EA's games, and has had nearly a decade of love-and-polish, across multiple platforms. It is really solid and worthy of attention.

Paul is a super-star. One of the best programmers I have ever had the pleasure of working with. After 18+ years at Maxis/EA he moved to Oculus in 2014, to join their stallion farm of talent. I am delighted for Paul to see his work made available outside of the EA castle walls.

Partial code for EASTL was released to [gpl.ea.com](http://gpl.ea.com) as part of the LGPL obligations for EAWebkit. [Paul Hodge](https://github.com/paulhodge) made a [Github repo](https://github.com/paulhodge/EASTL) of that partial drop in 2010, and has been maintaining it. I see that he has today updated the README for that repo to point to the new official EA one. Thanks for 6 years of work, Paul 🙂

I personally blogged about [EA's open source software](http://bobsummerwill.com/2014/06/25/ea-open-source-software/) in June of 2014, and followed that up with some action in July of 2014, with the [Fork me, EA!](https://kitsilanosoftware.wordpress.com/2014/07/31/fork-me-ea/) releases of all of the packages within EAWebkit. See [Github repos](https://github.com/kitsilanosoftware/EASTL). I'll revector my repos too.

Here were my pleas at the time of those releases:

  * _Step up to the plate, EA!_
  * _Build a community-friendly portal for these packages. Fork me back!_
  * _Re-add the missing source code, documentation and changelogs_
  * _Make these releases fully usable so that community members can contribute fixes and improvements_



And it appears that they have done exactly that.

Some other full packages lurking in there too - [EABase](https://github.com/electronicarts/EASTL/tree/master/test/packages/EABase) and [EATest](https://github.com/electronicarts/EASTL/tree/master/test/packages/EATest), and some partial code for others. Hopefully we'll see more opening up with time.

EABase was something which I put together in 2002, and which Ian Shaw took to a WW CTO meeting to pitch for me. And now 14 years later it is public.

I really hope that this is a sign of change within EA, and that we're going to see more open source releases from EA, and increased engagement of EA employees on external open source projects.

Good job, [Rob Parolin](https://twitter.com/RobParolin) and friends 🙂

![roberto](/assets/images/2016/02/roberto.jpg)

There is a new EA twitter account too - [@EAOpenSource](https://twitter.com/EAOpenSource) - which I imagine will be coming to life in the near future.

Get poking in there, everyone, and submit your [Issues](https://github.com/electronicarts/EASTL/issues) and [Pull Requests](https://github.com/electronicarts/EASTL/pulls) on Github!
