---
layout: post
title: "Ethereum Everywhere"
date: "2016-07-12 13:23:13 -0700"
permalink: /2016/07/12/ethereum-everywhere/
categories:
  - "Uncategorized"
featured_image: /assets/images/private.jpg
---

_" The Ethereum Foundation’s mission is to promote and support research, development and education to bring decentralized protocols and tools to the world that empower developers to produce next generation decentralized applications (dapps), and together build a more globally accessible, more free and more trustworthy Internet."_  
From <https://ethereum.org/foundation>

![Ethereum_logo_bw](/assets/images/ethereum_logo_bw.png)

## TL;DR - What are you proposing?

I am proposing to [the contributors](<https://github.com/ethereum/webthree-umbrella/wiki/Contributors>) that the C++ Ethereum client runtime ([cpp-ethereum](<http://www.ethdocs.org/en/latest/ethereum-clients/cpp-ethereum/>)) be re-licensed from the copyleft [GPLv3](<https://en.wikipedia.org/wiki/GNU_General_Public_License>) license to the more permissive [Apache 2.0](<https://en.wikipedia.org/wiki/Apache_License>) license, to enable Ethereum software to be used as broadly as possible ([a long-standing plan](<http://github.com/ethereum/wiki/wiki/Licensing>)). This proposal only addresses the C++ client runtime and does not include Solidity or Mix (the C++ tools).

There is [another blog post](<https://bobsummerwill.com/2016/07/12/c-re-licensing-plan/>) detailing the likely operational steps in that process. This document seeks to explain **why** I am making that proposal.

 

## What is Ethereum?

When we think about Ethereum, we usually think about public chain, and more specifically we think about **the public chain (the "mainnet")**. That is quite natural within the frame of reference of Ethereum purely as a cryptocurrency, but it is a limited view of the possibilities which this new decentralized computing platform offers.

Ethereum is much more than "a better cryptocurrency". Ether is the fuel for the engine, but **it is the Ethereum engine itself which opens up these new possibilities**. The fuel is just a means to an end.

We have the opportunity to build a set of technologies in the next few years which could have similar societal impacts as the Internet, the World Wide Web and open source languages, relational databases, etc. We are building a decentralized computing platform which every individual on Earth should benefit from.

[ ![tim](/assets/images/tim.jpg) ](<http://bobsummerwill.com/2016/07/12/ethereum-everywhere/tim/>)

[ ![linus-torvalds-ted](/assets/images/linus-torvalds-ted.jpg) ](<http://bobsummerwill.com/2016/07/12/ethereum-everywhere/linus-torvalds-ted/>)

These technologies need to reach into every nook and cranny of our computing fabric: big and small, public and private, independent and corporate; smartwatches to mainframes.

**This is**a large and ambitious undertaking that is addictive and all-consuming for many of us. Diversity of viewpoints, a broad spectrum of use-cases to mature the base technology, and an open and inclusive attitude and environment of collaboration will help us achieve our shared goals.**  
**

 

## Why do private and consortium chains matter?

![private](/assets/images/private.jpg)

_" It is important to note that while the original Ethereum blockchain is a public blockchain, the Ethereum state transition rules (i.e. the part of the protocol that deals with processing transactions, executing contract code, etc.) can be separated from the Ethereum public blockchain consensus algorithm (i.e. proof of work), and it is entirely possible to create private (run by one node controlled by one company) or consortium (run by a pre- specified set of nodes) blockchains that run the Ethereum code."_

_" Ethereum technology itself is thus arguably agnostic between whether it's applied in a public, consortium or private model, and it is our goal to maximally aim for interoperability between various instantiations of Ethereum - i.e. one should be able to take contracts and applications that are written for public chain Ethereum and port them to private chain Ethereum and vice versa."_

Vitalik Buterin, Ethereum Platform Review paper

![vitalik-buterin](/assets/images/vitalik-buterin.jpg)

Many individuals and companies, large and small, see that opportunity the Ethereum platform has to offer, and are equally supportive of and inspired by the technical vision, even if their business goals vary dramatically. Public chains and private or consortium chains will likely end up having a lot more in common than meets the eye.

We have a working example of a permissioned Ethereum chain in the form of [HydraChain](<https://github.com/HydraChain/hydrachain>), which was demonstrated at Ethereum DEVCON1 last November (2015):

Consortium chains can provide certain benefits beyond the general purpose public chain because they are special-purpose, such as:  


  * They can choose to have 1 second block-times.
  * They might not need to do any node-discovery because the nodes are fixed.
  * They can have incredible throughput (e.g. JP Morgan's Juno boasts 2,000 txns/sec).
  * They can modify consensus rules for performance (i.e. using PBFT).
  * They can be a testbed for experimentation and innovation, because there will often be much smaller groups of stakeholders.



The interest in Ethereum can be seen in the ever-growing volume of news stories about blockchain and decentralized ledger technologies in general, but in particular, the interest in the Ethereum platform emanating from major technology companies has escalated rapidly and noticeably since the last Ethereum developer conference, DEVCON1, which was held in London in November 2015.

The Ethereum platform is unique in the crypto space in that a significant number of large publicly owned corporations are either already using it, have experimented with it, or are exploring how it may be used in or integrated with their current systems.

The author believes providing a permissive licensing will facilitate moving towards the dream of mass adoption of the Ethereum platform.

Some articles from Vitalik Buterin on private and consortium blockchains:

  * [On Public and Private Blockchains (August 2015)](<https://blog.ethereum.org/2015/08/07/on-public-and-private-blockchains/>)
  * [Vitalik Buterin on Misconceptions in the Private vs Public Blockchain Debate](<http://coinjournal.net/vitalik-buterin-on-misconceptions-in-the-private-vs-public-blockchain-debate/>)
  * [Ethereum Platform Review: Opportunities and Challenges for Private and Consortium Blockchains](<https://www.scribd.com/doc/314477721/Ethereum-Platform-Review-Opportunities-and-Challenges-for-Private-and-Consortium-Blockchains> "View Ethereum Platform Review: Opportunities and Challenges for Private and Consortium Blockchains on Scribd")



 

## Why permissive licensing over copyleft?

Software licensing is obviously somewhat of a religious matter, but there are practical reasons to favor permissive licenses for low-level components like Ethereum.

[ ![stallman](/assets/images/stallman.jpg) ](<http://bobsummerwill.com/2016/07/12/ethereum-everywhere/stallman/>)

[ ![raymond](/assets/images/raymond.jpg?w=246&h=369&ssl=1) ](<http://bobsummerwill.com/2016/07/12/ethereum-everywhere/raymond/>)

Beyond incompatibility between the GPL and corporate business models there are practical ways in which the GPL reduces Ethereum's reach. The author was witness to these restrictions in his "past life" as a video games developer.

Worst of all are the games consoles. Code for PlayStation and XBOX usually has to be closed-source, because developers must sign NDAs (non-disclosure agreements) to be allowed access to the SDKs and they cannot redistribute those SDKs or any information about the platform APIs. That is commonly interpreted to include any code using those APIs. Some embedded platforms are similarly locked down.

While we could argue until the cows come home about the ethics of even using such systems, they are a reality, and [making Ethereum available on them has value](<https://www.reddit.com/r/ethereum/comments/4cuni0/would_you_like_to_see_mist_on_xbox_one/>).

The Apple stores - App Store for iOS and Mac Store for macOS - are incompatible with the GPL, and the same is likely true of the Windows Store. The Terms of Service are applying additional constraints which are [incompatible with the GPL](<https://www.fsf.org/blogs/licensing/more-about-the-app-store-gpl-enforcement>).

The only "workaround" which I have seen for this incompatibility is for there to be a single copyright owner for the software, such that they can dual license it as GPL and commercial, and for the commercial version of the software to be used in the App Store. That is the approach which Mono used for nearly a decade, which means that developers wanting to use C# on iOS had to pay for a commercial license for Mono for all that time.

Open Whisper Systems [recently](<https://whispersystems.org/blog/license-update/>) added an [exception to the GPLv3 license](<https://github.com/whispersystems/libsignal-protocol-c#license>) for their **libsignal-protocol-c** library, which permits people to incorporate that library into applications distributed through the App Store under Mozilla Public License 2.0, providing that the licensees are otherwise in compliance with the GPL. That exception looks similar to dual-licensing, but seemingly only applies for iOS.

That dual GPL/commercial licensing approach is a sensible approach for open-source friendly companies to take, which balances their desire to make the code available for public good while also generating revenue to keep them alive from those end-users who want or need to use the code in a context which is not GPL-compatible.

**Dual licensing is the approach which Mono took, which Qt have recently switched to and which Ethcore are following with Parity.****That dual licensing approach doesn 't work well for a Foundation, though, which is explicitly non-profit.**

The choice of GPL for a Foundation just reduces the contexts in which the code can be used, because offering a commercial license is not really possible. Commercial licensing would be incompatible with the non-profit mission of the Ethereum Foundation.

More importantly, though, the Foundation does not own the code to be able to offer the code under a commercial license, because the Foundation has intentionally not required copyright assignment from the contributors.

## What licenses does the Ethereum Foundation use?

At the moment we have a bit of a mixed bag. This proposal is only considering the C++ codebase, but it might make sense to look at licensing for the codebases as a whole.

  * go-ethereum - GPLv3 and LGPLv3
  * cpp-ethereum - GPLv3
  * pyethereum/pyethapp - MIT
  * ethereumjs-lib - MPL 2.0 and MIT
  * remix - MIT
  * web3.js - LGPLv3



 

## Why Apache 2.0?

There are numerous permissive software licenses which are [OSI approved](<https://opensource.org/licenses/alphabetical>), with a [much shorter list](<https://opensource.org/licenses>) of popular ones (really boiling down to MIT, BSD and Apache). Why are we favoring Apache 2.0 for the C++ codebase, where we had previously favored MIT?

 

![Floss-license-slide-image](/assets/images/floss-license-slide-image.png)

See [License compatibility](<https://en.wikipedia.org/wiki/License_compatibility>) from Wikipedia.

**It essentially boils down to compatibility with GPLv3 in combination with protection from future software patent claims, which is obviously hugely important to Ethereum.**

Apache 2.0 is the Free Software Foundation's own recommendation for permissive licences for that very reason:

-

_" This is a free software license, compatible with version 3 of the GNU GPL."_

_" Please note that this license is not compatible with GPL version 2, because it has some requirements that are not in that GPL version. These include certain patent termination and indemnification provisions. The patent termination provision is a good thing, which is _ _**why we recommend the Apache 2.0 license for substantial programs over other lax permissive licenses**."_

[Various Licenses and Comments about them, Free Software Foundation](<https://www.gnu.org/licenses/license-list.html#apache2>)

-

 

## About the Ethereum C++ client

The Ethereum C++ project has spent the last few months rebooting under the leadership of [Christian Reitwießner](<https://github.com/chriseth>), who is probably best known as the lead developer on Solidity, but also leads work on Mix, Remix and on the C++ client.

![christian](/assets/images/christian.jpg)

A number of the original C++ development team departed last year, with Christian, [Yann Levreau](<https://github.com/yann300>), [Liana Husikyan](<https://github.com/LianaHus>) and [Dimitry Khoklov](<https://github.com/winsvega/>) staying on. [Bob Summerwill](<https://github.com/bobsummerwill>) and [Greg Colvin](<https://github.com/gcolvin>) were added to the team in February, and [Paweł Bylica](<https://github.com/chfast>) rejoined the Foundation in March.

Christian has blogged about our progress in [February](<https://blog.ethereum.org/2016/02/12/ethereum-dev-update-c-roadmap/>), [May](<https://blog.ethereum.org/2016/05/04/c-dev-update-announcing-remix/>) and [July](<https://blog.ethereum.org/2016/07/08/c-dev-update-summer-edition/>).

[ ![cpp](/assets/images/cpp.png) ](<http://bobsummerwill.com/2016/07/12/ethereum-everywhere/cpp/>)

[ ![eth](/assets/images/eth.png) ](<http://bobsummerwill.com/2016/07/12/ethereum-everywhere/eth/>)

We are on the verge of [finally decoupling Solidity, (Re)Mix and Eth](<http://github.com/ethereum/webthree-umbrella/issues/639>), so that we have three entirely independent projects - one runtime, two tooling.

That architectural decoupling is a dual-edged sword, because that tight coupling did a lot to keep the eth client alive. We needed Solidity and Mix, so development on eth had to continue too. All of the projects were interrelated.

Following this refactoring, it is getting much harder to justify any significant level of spending from the Foundation for ongoing eth development. We already have geth. Parity is becoming more popular. There are 8 clients in total. In the early days, having the Foundation funding multiple clients was crucial for maturing the protocol. With 4 clients developed outside of the Foundation, it is harder to argue for this spending anymore.

So what unique value does a C++ client bring to the table to justify ongoing spending, whether from the Foundation or from other community actors?

The author's own interest in the C++ client was on the basis of [resource-constrained devices and portability](<https://doublethink.co/2015/11/30/first-working-ethereum-c-cross-builds/>), potential for the best raw performance, and a possibility that such a profile might also be a good fit for data centers. Those are interesting stories, but not entirely compelling. Parity has a very similar "profile".

**With this huge growth in interest in Ethereum for private and consortium chain scenarios though, we have a fantastic new potential "niche" for the C++ client, which is Enterprise applications.**

That wouldn't mean that the C++ client wouldn't support public chain scenarios. It would mean that we put an additional focus on modularity in the C++ client, so that it can start to span all of these categories in a way which has not been a primary focus to this point. And it would mean that additional resources could come to bear on this work, outside of purely being funded by the Ethereum Foundation.

 

## Why is the Ethereum C++ client a good fit for Enterprise?

Development efforts within large enterprises usually quite conservative in their development language choices. They need systems to run for many years, and favor long-term-service platforms and well known and mature development tools. That often ends up meaning Java or C++ on Linux.

**Newer languages like Go and Rust are less appealing in many corporate environments, because their developers have little to no experience with those languages, where they have Java and C++ experience to spare.**

In addition, the C++ codebase benefited from a [fairly significant refactoring](<https://gavofyork.gitbooks.io/turboethereum/content/poa.html>) last year which started to decouple the consensus mechanism. This was prototyped as a Proof of Authority (POA) alternative to Proof of Work (POW) in the (now retired) Fluidity client.

There has been huge interest in Ethereum integration within the [Hyperledger consortium](<http://hyperledger.org>) following [Vitalik's presentation](<http://www.coindesk.com/vitalik-buterin-addresses-hyperledger-possible-ethereum-integration/>) to their Technical Steering Committee in April 2016. Hyperledger is a project under the Linux Foundation bringing together many [member companies](<https://www.hyperledger.org/about/members>) collaborating to build common blockchain and ledger solutions.

Outside of Hyperledger there are other companies who have already made their technology decision and chosen Ethereum as their base technology. [Rubix by Deloitte](<http://rubixbydeloitte.com>), for example, have been building on the C++ codebase for several months and there are a number of other companies also favoring the C++ codebase.

With permissive licensing, work in any of these "C++ buckets" could proceed in parallel with existing Ethereum Foundation-centered work. We can collaborate where we have commonality and diverge where we need to.

**Permissive licensing enables permissionless innovation.**

 

 

## Corporations don't love you or hate you

![Screen Shot 2016-06-26 at 10.51.00 PM](/assets/images/screen-shot-2016-06-26-at-10-51-00-pm.png)

Technology companies are now **the** [largest corporations in the world](<https://en.wikipedia.org/wiki/List_of_public_corporations_by_market_capitalization#2016>) by market cap.

Apple, Alphabet/Google, Microsoft and Amazon are literally #1, #2, #3 and #4 for the first quarter of 2016. Ahead of oil companies. Ahead of banks. Ahead of every other industry.

Most software developers are working for large corporations. Those corporations need tools to build their businesses. Open source tools resourced by large corporations are now the norm. There is a world of difference between the current day and the hostile landscape which Richard Stallman was facing in the mid-80s.

  * Apple are obviously a money-making machine, but they also finance LLVM/Clang.
  * Google do not have your best interests at heart, but that doesn't mean that Go is evil.
  * Facebook, mixed in with their people farming, have brought us React.
  * Microsoft are night-and-day different from the Ballmer horror days.



## Conclusion

Corporations will build blockchain technology irrespective of what we do. It is already happening.

Just as both Intranets and the Internet have a role to play, so do public and private/consortium chains. Maximalist thinking is not particularly helpful here.

**The real world never works in black-and-white, and demonizing people with similar but not identical goals is self-defeating.**

The author would rather have those corporations building Ethereum-based blockchain technology than have them building something completely incompatible purely because of the barrier of copyleft licensing which we have long planned to remove anyway.

Having these corporations within a shared "big tent" rather than in rival camps gives us maximal synergy, and taps the vast resources of those corporations to contribute to our goals, rather than letting them build rival ecosystems with zero synergy.

**Proceed with caution, but please let 's proceed!**

![Proceed-with-Caution-State-Farm](/assets/images/proceed-with-caution-state-farm.jpg)

 

 

### Appendix A - History of cpp-ethereum licensing

  * [Issue #3 - License (January 2014)  
](<https://github.com/ethereum/cpp-ethereum/issues/3>)
  * [Vitalik changed it to MIT License (January 2014)  
](<https://github.com/ethereum/cpp-ethereum/commit/e10bf35879318384814e0f82c29bf08665f394c7>)
  * [Gav reverted it to GPL (August 2014)](<https://github.com/ethereum/webthree-umbrella/commit/2f524f645b536782085cc2f0be79289479f73d44>)
  * ["License is and always has been GPL - Gav" (October 2014)](<https://github.com/ethereum/cpp-ethereum/issues/3#issuecomment-57935523>)
  * [Issue #575 - Split projects, re-licence libraries as more permissive (December 2014)](<https://github.com/ethereum/cpp-ethereum/issues/575>)
  * [Pull #1392 - Suggestion for contributor license (March 2015)](<https://github.com/ethereum/cpp-ethereum/pull/1392>)
  * [Pull #2789 - Wording for MIT license and external contributors (August 2015)](<https://github.com/ethereum/cpp-ethereum/pull/2789>)
  * [Issue #530 - Get to clarity on licensing and copyright (May 2016)](<http://github.com/ethereum/webthree-umbrella/issues/530>)



### Appendix B - A selection of Enterprise blockchain articles and events

  * March 2015 
    * [Former JPMorgan Exec Blythe Masters Swaps Wall Street for Bitcoin](<http://www.coindesk.com/former-jp-morgan-exec-blythe-masters-swaps-wall-street-for-bitcoin/>)
  * April 2015 
    * [Consensus-as-a-service: a brief report on the emergence of permissioned, distributed ledger systems](<http://www.ofnumbers.com/2015/04/06/consensus-as-a-service-a-brief-report-on-the-emergence-of-permissioned-distributed-ledger-systems/>) (Tim Swanson)
  * July 2015 
    * [Inside R3CEV's Plot to Bring Distributed Ledgers to Wall Street](<http://www.coindesk.com/r3cev-distributed-ledger-wall-street/>)
  * August 2015 
    * [On Public and Private Blockchains](<http://www.reuters.com/article/us-banks-blockchain-idUSKCN0RF24M20150915>) (Vitalik Buterin)
    * [ConsenSys Emerges From Stealth with New Website](<http://www.coindesk.com/press-releases/consensys-emerges-stealth/>)
  * September 2015 
    * [Nine of world's biggest banks join to form blockchain partnership](<http://www.reuters.com/article/us-banks-blockchain-idUSKCN0RF24M20150915>)
  * October 2015 
    * [Microsoft Partners With ConsenSys To Use Ethereum To Provide Blockchain-As-A-Service](<http://techcrunch.com/2015/10/28/microsoft-partners-with-consensys-to-use-ethereum-to-provide-blockchain-as-a-service/>)
  * December 2015 
    * [Linux Foundation Unites Industry Leaders to Advance Blockchain Technology](<http://www.linuxfoundation.org/news-media/announcements/2015/12/linux-foundation-unites-industry-leaders-advance-blockchain>)
  * January 2016 
    * [R3 Completes Blockchain Test With 11 Banks](<http://www.coindesk.com/r3cev-blockchain-test-11-banks/>)
  * February 2016 
    * [ConsenSys Joins Linux Foundation Blockchain Initiative  
](<http://us11.campaign-archive2.com/?u=947c9b18fc27e0b00fc2ad055&id=7e704a14c4&e=e307a83fc2#awesomeshare>)
    * [IBM has just open-sourced 44,000 lines of blockchain code on GitHub](<http://thenextweb.com/apps/2016/02/16/ibm-has-just-open-sourced-44000-lines-of-blockchain-code-on-github/>)
    * [IBM Exec Elected Chair of Hyperledger Blockchain Committee](<http://www.coindesk.com/ibm-exec-elected-chairman-of-hyperledger-technical-steering-committee/>)
  * March 2016 
    * [40 Banks Trial Commercial Paper Trading in Latest R3 Blockchain Test](<http://www.coindesk.com/r3-consortium-banks-blockchain-solutions/>)
    * [JPMorgan Unveils 'Juno' Project at Hyperledger Blockchain Meeting](<http://www.coindesk.com/jpmorgan-juno-hyperledger-blockchain/>)
    * [Meet the Technical Minds Behind the Hyperledger Blockchain Project](<http://www.coindesk.com/hyperledger-technical-steering-committee/>)
    * [Hyperledger On Verge of Merging Blockchain IBM, Digital Asset Code](<http://www.coindesk.com/hyperledger-on-the-verge-of-merging-blockchain-code-from-ibm-digital-asset/>)
    * [Microsoft Adds Ethereum to Windows Platform For Over 3 Million Developers](<http://www.coindesk.com/microsoft-ethereum-3-million-developers/>)
  * April 2016 
    * [R3 Blockchain Consortium Partners With Microsoft](<http://www.coindesk.com/consortium-of-global-banks-formalizes-partnership-with-microsoft/>)
    * [Introducing R3 Corda: A Distributed Ledger Designed for Financial Services](<http://r3cev.com/blog/2016/4/4/introducing-r3-corda-a-distributed-ledger-designed-for-financial-services>) (Richard Gendal Brown)
    * [Intel Unveils 'Sawtooth Lake' Proposal at Hyperledger Meeting](<http://www.coindesk.com/intel-sawtooth-lake-distributed-ledger-proposal/>)
    * [Intel Conducting Experiments to Massively Scale Blockchain](<http://www.coindesk.com/intel-hardware-security-blockchains/>)
    * [Vitalik Buterin Pitches Hyperledger Project on Ethereum Integration](<https://www.coindesk.com/vitalik-buterin-addresses-hyperledger-possible-ethereum-integration/>)
  * May 2016 
    * [China Joins the Blockchain Race With ChinaLedger Alliance](<http://www.nasdaq.com/article/china-joins-the-blockchain-race-with-chinaledger-alliance-cm614734>)
    * [Cats and dogs can be friends](<https://bobsummerwill.com/2016/06/12/cats-and-dogs-can-be-friends/>) (Bob Summerwill)
    * [Apache Foundation Founder Named Hyperledger Executive Director](<http://www.coindesk.com/hyperledger-appoints-first-executive-director-apache/>)
  * June 2016 
    * [Opportunities and Challenges for Private and Consortium Blockchains](<http://r3cev.com/s/Ethereum_Paper-97k4.pdf>) (Vitalik Buterin)
    * [31 Chinese Firms Form Financial Blockchain Consortium  
](<http://www.coindesk.com/financial-blockchain-shenzhen-consortium-launch/>)
  * July 2016 
    * [Russian Finance Firms Form Blockchain Consortium](<http://www.coindesk.com/russian-finance-firms-form-blockchain-consortium/>)
