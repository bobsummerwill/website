---
layout: post
title: "Background on Ethereum client licensing"
date: 2022-11-30
---

On 23rd November 2022, [Alexey Sharp](https://twitter.com/realLedgerwatch) of the [Erigon team](https://twitter.com/ErigonEth) announced that Erigon were [winding down support](https://twitter.com/ErigonEth/status/1595479897220055041) for the [Akula client](https://github.com/akula-bft/akula) which they had been developing for nearly two years. During that time there were [722 commits from 21 contributors](https://github.com/akula-bft/akula/graphs/contributors), with the vast majority being single-handed work from [Artem Vorotnikov](https://github.com/vorot93). The Erigon team took this action in the face of another Rust client on the [verge of announcement](https://twitter.com/gakonst/status/1595648232226291712) from Paradigm. They decided that they could not compete with Paradigm's resourcing and that it did not even make sense to try, so they have terminated their investment into Akula.

It is very disappointing to see another yet Ethereum client die for non-technical reasons. This has happened a number of times in the history of the project and always feels like a gut-punch. Alexey was very diplomatic. Artem was not so diplomatic, and neither was I.

> This is a really shameful situation.
> It is not the first time that an open source Ethereum client project has been killed by self-motivated commercial concerns.
> It is not the second time either.
> It is not the third time either.
> It is actually the fourth.
>
> — Bob Summerwill (@BobSummerwill) [November 23, 2022](https://twitter.com/BobSummerwill/status/1595560707298557952)

Alexey has published a number of vlogs in the last couple of weeks, laying out the background to their current situation and his understanding of some of the root causes here, especially related to software licensing. I would recommend watching at least "Winding down support for Akula – discussion" and "Software licensing and my apology" as background to understand why I am writing this blog post.

In those videos, Alexey addressed myself and the Parity team to bring up some prior history with regard to open source licensing which informed his choices for Akula. Essentially, what is the scoop with Apache 2.0 and GPLv3 licensing, CLAs (contributor licensing agreement), DCOs (developer certificate of origin), and so on? How have particular teams choices on licensing informed these kind of situations?

- Nov 11 – [Erigon funding, goal, and support](https://rumble.com/v1xlohe-erigon-funding-goal-and-support.html)
- Nov 12 – [Why I am making these videos (and when I am going to stop)](https://rumble.com/v1xlxyi-why-i-am-making-these-videos-and-when-i-am-going-to-stop.html)
- Nov 13 – [Closed source Ethereum implementations, Transaction Pool component](https://rumble.com/v1xm1k8-closed-source-ethereum-implementations-transaction-pool-component.html)
- Nov 16 – [Reasons for limited support for long chains like BSC, Bor/Polygon, and the future](https://rumble.com/v1xmqt4-reasons-for-limited-support-for-long-chains-like-bsc-borpolygon-and-the-fut.html)
- Nov 20 – [Very short video – Our team meeting last week and "poisoning"](https://rumble.com/v1xn24m-very-short-video-our-team-meeting-last-week-and-poisoning.html)
- Nov 24 – [Winding down support for Akula project – discussion](https://rumble.com/v1xn83c-winding-down-support-for-akula-project-discussion.html)
- Nov 26 – [Software licensing and my apology](https://rumble.com/v1xneeu-software-licensing-and-my-apology.html)
- Nov 28 – [Blockchain zoo and my view on the future](https://rumble.com/v1xo5uc-blockchain-zoom-and-my-view-on-the-future.html)

## Software licensing in a nutshell

Software licenses are not specific to blockchain. They have been a key feature of free and open source software (FOSS) for nearly 40 years now. Software licensing itself is informed by [copyright law](https://en.wikipedia.org/wiki/Copyright) going back for centuries. Copyright holders (usually the authors of the code) have the right to determine how their publications can be used.

Software is usually released with a corresponding license file which makes those terms clear. If there are violations of those terms by users or by other developers then the license would be the basis of a court case on breach of terms. People can chose to violate those terms, but the license is the credible threat which discourages such behaviour.

[Richard Stallman](https://en.wikipedia.org/wiki/Richard_Stallman) launched the [GNU Project](https://en.wikipedia.org/wiki/GNU_Project) in 1983 and the [Free Software Foundation](https://en.wikipedia.org/wiki/Free_Software_Foundation) in 1985 and the [GPL (GNU General Public License)](https://en.wikipedia.org/wiki/GNU_General_Public_License) license in 1989, all as part of a personal fightback against commercial licensing which was impeding his personal freedom and freedoms of all of humanity to use software as they saw fit. In particular, this family of licenses introduced the concept of [Copyleft](https://en.wikipedia.org/wiki/Copyleft), which uses the Copyright system against itself, to "lock open" particular software freedoms for all users. In particular any "derived works" are obliged to be licensed under the same terms.

[Free Software Definition](https://en.wikipedia.org/wiki/The_Free_Software_Definition) as defined by the Free Software Foundation defines these fundamental freedoms:

- The freedom to run the program as you wish, for any purpose (freedom 0).
- The freedom to study how the program works, and change it so it does your computing as you wish (freedom 1). Access to the source code is a precondition for this.
- The freedom to redistribute copies so you can help your neighbor (freedom 2).
- The freedom to distribute copies of your modified versions to others (freedom 3). By doing this you can give the whole community a chance to benefit from your changes. Access to the source code is a precondition for this.

Permissive licensing became dominant in later years with the birth of the [open source movement](https://en.wikipedia.org/wiki/Open_source) in the late 90s and especially around the open sourcing of the Netscape Browser which led to Mozilla. Where Richard Stallman and the FSF focused on "free software" and "free as in freedom", the open source movement focus on the practical benefits of open source for businesses, without the ethical lecturing, and were hugely successful in that new focus. Permissive licenses were nothing new, but found fresh focus with the [Open Source Definition](https://en.wikipedia.org/wiki/The_Open_Source_Definition) and the [OSI (Open Source Initiative)](https://en.wikipedia.org/wiki/Open_Source_Initiative) non-profit who steward that definition.

Permissive licensing is a subset of that Free Software Definition in which authors of derived works are not obliged to make their modifications available.

## CLAs and DCOs

Two commonly seen acronyms for open source projects are [CLA (Contributor License Agreement)](https://en.wikipedia.org/wiki/Contributor_License_Agreement) and [DCO (Developer Certificate of Origin)](https://en.wikipedia.org/wiki/Developer_Certificate_of_Origin), which are fairly similar concepts. Both record an agreement provided by each contributor to a particular project stating that they authored the code and have the right to submit it under the license used by the project. This might seem somewhat redundant but it can be essential to legal certainty for a project.

Without any such agreement a common workflow is that anybody can submit a Pull Request against a project on Github and as long as its maintainers are happy with the changes and it does not break anything then it gets merged. All good, right? Well, not really no, because you don't necessarily know who the contributor was. They might be using a pseudonym. They might have cut-and-pasted code from elsewhere. The code might have patent encumbrances, might be copyrighted by somebody else, might have come from a company who might then have a claim against the project. You have accepted code and the contributor could completely ghost you and you are left with the damage in later years.

DCO was not introduced in the Linux Foundation for theoretical reasons. It was in direct response to [submarine patents](https://en.wikipedia.org/wiki/Submarine_patent) introduced into the Linux kernel. At one point Microsoft had a [$1B per year "business" in patent trolling](https://www.fiercewireless.com/wireless/samsung-paid-microsoft-1b-last-year-patent-royalties-related-to-android) of this kind against Samsung for their use of that kernel in their Android devices.

Here is an example of the DCO used for the majority of Linux Foundation projects.

![DCO example](/website/assets/images/2022/11/screen-shot-2022-11-28-at-4.37.12-pm.png)

## Use of open source software within corporations

Large corporations have a major administrative task tracking what software is being used within their enterprise. Most software is broken down into small components, each of which might have different licensing terms (some commercial, some open source), and companies are likely using thousands of these components at any given time. Maybe multiple versions of many of them. Managing this complexity has become a field of endeavour in its own right, called [software supply chain](https://en.wikipedia.org/wiki/Software_supply_chain).

One primary reason for such tracking is related to vulnerabilities for such components and working out how your own systems are impacted when such vulnerabilities are announced. Another reason is for tracking licensing and the potential risk coming from exposure to particular licenses. Over permissive licenses provide no protection from submarine patents. Copyleft licenses run the risk of accidental "viral contagion" where your company might face legal action over intentional violation of a GPL-family license for one component used in one of your many software projects. Thousands of software engineers have the potential for unintentionally introducing such risk.

That risk can be managed with careful use of GPL components but many large enterprises just cannot tolerate any such risk and so have a blanket ban on GPL-licensed software. I have been witness to exactly this workflow during my time as a software engineer on AAA videogames at EA.

So, for maximum use of software, permissive licenses are usually the best choice, with Apache in particular also adding patent protection over even more permissive licences like MIT and BSD. That patent protection takes the form of obliging contributors to grant a license for any patents they hold related to their contributions. It does not make the patents go away but it nullifies the potential for submarine patents being introduced by the contributors. It also cannot protect against patents outside of the project contributors which apply to the code. The best defence there is collective patent pooling.

## Hyperledger @ Linux Foundation

The author spent five very tedious months attempting to rectify ambiguous licensing for the cpp-ethereum Ethereum client in 2016 which failed at the last minute.

Hyperledger was starting.

Brian Behlendorf. HL insisted on Apache Epicenter interview with Brian B – explaining Apache 2 Enterprise friendly plus patent But not reason for putting into Hyperledger

Work on that C++ codebase had been defunded by the Ethereum Foundation in late 2015 as the funds for the EF were running chronically short. Gavin Wood, Co-Founder and CTO for Ethereum, left to form his own for-profit company called Ethcore (later Parity Technologies) and built the Parity (later Parity-Ethereum) client from scratch in the then-very-new Rust programming language, with many of his former C++ team members joining him in that endeavor. Spending on cpp-ethereum was cut to the bone. In February 2016 with runway extended by rising ETH prices, Bob Summerwill, Greg Colvin and Pawel were hired and the cpp-ethereum project rebooted under Christian R.

There was a clear need for a C++ codebase in the opinion of the author. Whether or not cpp-ethereum could be iterated into that good codebase was an open issue. Lots of work was required to get things back into a workable state. That was happening in parallel with the author's relicensing project.

Why? To make Ethereum available to everyone everywhere, which was a goal from the very start of the project, to "liberalize the core". There had been a prior MIT relicensing effort which was abandoned, so the author took that work on. Then Parity spiked it at the last minute, to protect their own commercial interests, and from fear of what having IBM's nose "under the tent" could lead to. IBM ready with their 10 people. Others interested too – like Rubix by Deloitte – and many companies in Asia, such as AMIS. A lot of this was time critical because of Fabric 1.0 release timeline and Corda releases. IBM could have revectored on top of Ethereum. Those three reasons.

[Ethereum Everywhere](https://bobsummerwill.com/2016/07/12/ethereum-everywhere/) blog post July 2016.

[Hyperledger Project reflects on blockchain politics](https://www.ibtimes.co.uk/hyperledger-project-reflects-blockchain-politics-1603381), Jan 2017.

Anyway – all that went down the shitter and so we went to EEA instead. The codebase was never adequately resourced from that point and died as was very predictable.

## What did Parity do right?

Gavin learnt from his experience with cpp-ethereum and instituted CLAs from day one so there was no ambiguity about provenance for external contributions. The code was dual licensed as GPLv3 and Commercial, so that Parity could sell the code to enterprises where GPL licensing was unacceptable, and/or provide consulting for customizations to that codebase.

They kept things going during Shanghai attacks.

One downside of that approach was that external contributors essentially handed their work over to Parity who then had the exclusive right to commercialize that work. Other companies could not compete on the same basis to provide Parity support or customization. Also, the GPLv3 licensing made the codebase unappealing in general to enterprises who would have to pay for those commercial licenses even to consider using Parity. Only Parity could provide that support and they were a very small startup. That in itself ruled out Parity for many. The author was witness to this first hand within the EEA member companies.

## The failure of OpenEthereum

That CLA meant they could relicense at will, which was good for them. They were able to remove the "commercial" clause.

Unfunded by the EF for many years, Story of the eventual grants from EF but then they fucked off anyway.. Code dev defunded by Parity in 2017 and rotting for 3 years prior to the OpenEthereum DAO stuff. Alexey offered his apology to Parity and Fred CTO of Parity for saying that we would not participate unless relicensed and so did the author, but I think that was fine and right. Nobody but Gnosis chose to help under their terms and they found it impossible to keep the thing going.

## Silkworm and Akula

Erigon team started to build silkworm product around evmone Why did evmone happen? Licensing. No developers flocked from IBM to Silkworm though they did not do much promotion Chose Apache for Akula because of that general understanding. Perhaps GPL would have stopped Paradigm? More defensive around information sharing in the future? Correct thing would have been to contribute Not necessarily, it was the stealth which was the issue.

## Would GPLv3 licensing have saved Akula?

No, imho.

GPLv3 licensing would deter a company planning to take advantage of permissive licensing to make a closed source commercial product, but it would not deter anybody from making another GPLv3 codebase, or from starting with a fork of GPLv3 code and then replacing it piecemeal with permissively licensed components.

From what I can see, GPLv3 would have made no difference to Paradigm's actions. The author agrees with Alexey that anybody has the right to fork open source projects and use the code in whatever way they see fit, as long as they comply to the licensing terms. That is enshrined as one of the key freedoms, in fact 🙂

Where Paradigm's actions were borderline unethical and certainly not nice was their stealth approach where they gathered information from the Akula team and then used that information to their own advantage in building a competing product behind closed doors. That stealth wasted time for the Akula team who could have made their decisions months earlier. It also tainted the good will and collaboration which could have been built between the teams.

Did they re-use source code from Akula? That remains to be seen but their CTO [asserts that is not the case](https://twitter.com/gakonst/status/1595648232226291712). What they certainly have done is replicated the Erigon architecture. Doubtless they will have some similar or identical components which may or may not have built on Akula implementation.

Alexey has said that as a consequence of these events that the Erigon team is becoming less open in their communication and public stance. They got burned and are now wary as a consequence. Working in public is not an easy thing to do and you really don't want others to take advantage of that good-will information sharing, but sadly that is what appears to have happened here.
