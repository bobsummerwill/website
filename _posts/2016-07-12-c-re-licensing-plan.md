---
layout: post
title: "C++ re-licensing plan"
date: "2016-07-12 13:23:44 -0700"
permalink: /2016/07/12/c-re-licensing-plan/
featured_image: /assets/images/2016/06/cpp.png
---

## Overview

This is a proposal to re-license the C++ implementation of the Ethereum client runtime ([cpp-ethereum](http://www.ethdocs.org/en/latest/ethereum-clients/cpp-ethereum/)) from the copyleft [GPLv3](https://en.wikipedia.org/wiki/GNU_General_Public_License) license to the permissive [Apache 2.0](https://en.wikipedia.org/wiki/Apache_License) license, to enable Ethereum to be used as broadly as possible.

**NB: If you would like to discuss this plan, please let 's all do so on [cpp-ethereum](https://gitter.im/ethereum/cpp-ethereum) Gitter channel. Thanks!**

Moving to permissive licensing has been the ["plan of record"](https://github.com/ethereum/wiki/wiki/Licensing) for a year or so, which we are belatedly executing on. Gavin Wood actually started the process of relicensing to MIT last year, but it was never completed. So we're going through the process again now.

There is [another long-form article](https://bobsummerwill.com/2016/07/12/ethereum-everywhere/) talking about the rationale for the change and the history leading up to this proposed change of licensing, so I won't duplicate that content here.

This post talks through the expected **operational steps** for making this change. These steps aren't entirely sequential, and we will be doing overlapping steps in parallel wherever we can, to try to get through the tedious process as quickly as we can.

Ultimately the contributors to the C++ codebase will make the decision on whether or not we relicense, and there is no intention from the Ethereum Foundation to "force" the process.

 

 

### Steps to be followed

  * Creation of a [Github issue](https://github.com/ethereum/cpp-ethereum/issues/3218) to start the ball rolling _[started May 25th]_
  * Start to gather contributor details ([Piratepad](http://piratepad.net/g9A0NTQjcI), then [Wiki](https://github.com/ethereum/webthree-umbrella/wiki/Contributors)) _[completed July 7th]_
  * Mention in [the](https://github.com/ethereum/webthree-umbrella/releases/tag/v1.2.6) [last](https://github.com/ethereum/webthree-umbrella/releases/tag/v1.2.7) [few](https://github.com/ethereum/webthree-umbrella/releases/tag/v1.2.8) [releases](https://github.com/ethereum/webthree-umbrella/releases/tag/v1.2.9) that we are contacting contributors  _[May, June, July]_
  * Ad-hoc conversations with contributors on the issue, Gitter, email  _[Ongoing]_
  * Talk to an IP lawyer to verify what we need to do, in rough strokes  _[June 22nd]_
  * Publicize "the plan" and work through any disagreements  _[July 12th onwards]_
  * Distribute paperwork to all contributors  _[August 18th to August 24th]_
  * Complete the process and change the license
  * Announce that change to the world



 

![apache](/website/assets/images/2016/06/apache.gif)

### What is the paperwork?

Everybody [who has contributed](https://github.com/ethereum/webthree-umbrella/wiki/Contributors) to the code in question (see below) will be sent a letter, probably both as a PDF and physically, which essentially attests to the fact that they were the author of that code, and giving their approval for that contribution to be used under the Apache 2.0 license.

Future contributors will be required to make a similar declaration. The one page document just ensures that there is no ambiguity for any party in the case of future disagreement or legal action.

_Here is a[template for the paperwork](https://drive.google.com/open?id=1C5LEvZ5CrmxuZdBew2ChRUk5NK72Lp1q1wiZaG9ujko), which is legal boilerplate from the Linux Foundation adjusted to our project._

**This is not final paperwork.** **Discussion ongoing.**

 

### Content to be relicensed

The following repositories are in the process of being reorganized into a restored [cpp-ethereum](https://github.com/ethereum/cpp-ethereum) repository, which will be relicensed as Apache 2.0:

  * [libethereum](https://github.com/ethereum/libethereum)
  * [libweb3core](https://github.com/ethereum/libweb3core)
  * [webthree](https://github.com/ethereum/webthree)
  * [webthree-helpers](https://github.com/ethereum/webthree-helpers)



That will include the following applications:

  * Ethereum VM: 
    * eth
    * ethvm
  * Unit-testing: 
    * testeth
    * testweb3
    * testweb3core
  * Support tools: 
    * bench
    * ethkey
    * ethminer
    * rlp



The following standalone repositories will also be relicensed to Apache 2.0:

  * [cpp-dependencies](https://github.com/ethereum/cpp-dependencies)
  * [evmjit](https://github.com/ethereum/evmjit)



The following repositories, containing the Solidity compiler and the deprecated C++ GUI applications will remain under GPLv3:

  * [alethzero](https://github.com/ethereum/alethzero)
  * [mix](https://github.com/ethereum/mix)
  * [solidity](https://github.com/ethereum/solidity)



The following repository, containing the new "Remix" debugging components will remain under MIT, though we might want to consider whether that should be Apache 2.0 as well?

  * [remix](https://github.com/ethereum/remix)
