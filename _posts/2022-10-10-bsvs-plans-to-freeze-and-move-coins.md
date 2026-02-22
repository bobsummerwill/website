---
layout: post
title: "BSV’s plans to freeze and move coins"
date: "2022-10-10 22:18:22 -0700"
permalink: /2022/10/10/bsvs-plans-to-freeze-and-move-coins/
---
![screenshot 2023 03 22 at 6.40.49 pm](/assets/images/2023/03/screenshot-2023-03-22-at-6.40.49-pm.png)



There have been rumblings for years about the BSV project's plans related to "court orders".  
  
The Bitcoin (BSV) Association dropped a bombshell on 5th October 2022, announcing their [Digital Asset Recovery Process](https://www.bitcoinsv.io/digital-asset-recovery) and releasing the [Blacklist Manager](https://www.bitcoinsv.io/blacklist-manager). This is the closest that we have seen to on-chain censorship for any blockchain, and the censorship is just the first step. The second step is reassignment of assets to other owners with no private keys required.

Further details are provided in the [Blacklist Manager Technical Manual](https://bitcoin-association.gitbook.io/blacklist-manager/).

Here is the explainer video:

[ ![](/website/assets/images/2022/10/explainer-1.png)](https://www.youtube.com/watch?v=xLRp7zxeTfM)

The Blacklist Manager is described as **" A required add-on to the Bitcoin SV node software to ensure that miners comply with court orders"**.  
  
Furthermore, **" A miner who does not install Blacklist Manager risks being out of consensus with other nodes on frozen UTXOs. This could lead to their blocks being orphaned by the rest of the network if they are spending these frozen UTXOs."**

What is the context?

Craig Wright has been claiming for years that Bitcoin can be moved without private keys and that developers have a fiduciary duty to reassign stolen coins if they are ordered to do by courts. The developers have the power to do that, he argues, and so they must do so. Until this software was released it was unclear how such an out-of-left-field assertion was even possible.

It seems likely that these "court order" moves within the BSV ecosystem are directly related to Craig Wright's claim that 110,000K bitcoins were stolen from him on or around 5th February 2020 in the notorious "Pineapple Hack". He wants those coins to be recognized as his property and for them to be reassigned to him.  
  
_(Incidentally - he claims ownership of the infamous "1Feex" address which received funds from the Mt Gox hack in 2011. So the funds his claims were stolen from him were themselves previously stolen goods. What about the property rights of their original owners?)  
_  
Such reassignment obviously requires changes to the BSV software, because blockchain transactions always require private keys to move funds. These releases from the Bitcoin (BSV) Association and nChain appear to be the changes to support such actions.

Some history on this saga:

  * [Tulip Trading Limited - Letter Before Action](/website/assets/images/external/misc/a1letter-before-action-from-ttl.pdf) - 24th February 2021
  * [Dr. Craig Wright/Tulip Trust Statement](https://bitcoinassociation.net/bitcoin-association-statement-concerning-legal-action-by-dr-craig-s-wright-tulip-trading-ltd/) - 26th February 2021
  * [Bitcoin SV Node software – Upgrade to v1.0.9 Release](https://www.bitcoinsv.io/releases/bitcoin-sv-node-software-upgrade-to-v1-0-9-release) - 19th October 2021
  * [Bitcoin Association for BSV – Tulip Trading Ltd. Settlement Statement and FAQ](https://bitcoinassociation.net/bitcoin-association-for-bsv-tulip-trading-ltd-settlement-statement-and-faq/) on 10th June 2022.
  * Notice below published in the Financial Times on 30th June 2022, with an deadline on "competing claims" to these coins which expired at the end of September 2022.
  * [Digital Asset Recovery Process](https://www.bitcoinsv.io/digital-asset-recovery) announced and Blacklist Manager announced on 5th October 2022.



![](/website/assets/images/2022/10/letter-to-ft.jpg)

How is this tooling supposed to work?

Here are the stages in the workflow, with Step 4 being where the miners "choose" to prioritize orders from the Blacklist over the existing "longest chain" Nakamoto Consensus which has been the consensus mechanism for Bitcoin since the very first mined block. The Blacklist Manager is in control of which transactions miners can or cannot mine.

![](/website/assets/images/2022/10/flow.png)

In the final phase of the **Digital Asset Recovery Process** (not yet implemented it seems, but explained in the video), the miners would also receive orders from the Notary to **reassign assets** and the miners would follow their orders on that as well as on the freezes.

![](/website/assets/images/2022/10/order3.png)

It is unclear exactly how that asset reassignment would work, but conversations on Twitter point to that likely being either forcing of an invalid transaction by the miners or by addition of a new transaction type which could transfer funds with no need for private keys. Both of these options would constitute a soft fork or hard fork and would be a change of consensus.

How would forcing an invalid transaction work? Wouldn't the other full nodes reject it? No. There are very few full nodes in BSV except those run by the miners, because they are too expensive to run. The only exception are a small number of infrastructure providers, but many of those will hit the same kind of scale issues which [Blockchair hit](https://github.com/Blockchair/Blockchair.Support/issues/910#issuecomment-1159369293) causing their nodes to crash. In the explanation of that event, they explained:  
  
`"But the reality is that 99.99% or so of Bitcoin SV transactions are junk, so despite being the biggest Bitcoin-like blockchain with most transactions, Bitcoin SV constitutes only 0.3% of our visitor numbers and there are very few API clients using Bitcoin SV (0.2% of all API requests most of which are free API calls for the stats). Unfortunately, this doesn't cover all these costs. So that's why we can't run more than 2 nodes, and even **these two nodes will get stuck at some point because we'll go bankrupt buying all these disks to store the junk data**. But we're trying our best :)"`  


It is somewhat unclear from the [Blacklist Manager Technical Manual](https://bitcoin-association.gitbook.io/blacklist-manager/) whether miners can connect to multiple Notaries in parallel or only to a single notary.

Assuming a multiple-notary scenario it would be impossible for miners would stay in consensus unless they were all following the exact same list of notaries. All the miners must move in lockstep to avoid orphaning.

Lockstep, why?

Here is an example of the lockstep issue, [first tweeted](https://twitter.com/BobSummerwill/status/1580668028756557824.) shortly after the initial release of this article.

  * Miner A and Miner B (majority hash together) are connected to Notary X and Y.
  * Miner C (minority hash) is only connected to Notary X.
  * Notary Y issues a freeze command and "baddie" tries to move those funds.
  * Miner C does not receive that particular freeze order and mines a block moving those funds.
  * Any blocks generated by Miner C containing those "baddy transactions" will be orphaned by miners A and B.
  * This can happen repeatedly to Miner C and he does not even know why he is being orphaned.
  * Miner C is losing money every time this happens.
  * The only way to avoid this scenario is for all miners to follow exactly the same notaries as the majority hash miners.



Court orders might be mutual incompatible between countries too, meaning that some legal orders must be ignored. A simple example here would be enforcement of sanctions, as highlighted by the recent Tornado Cash OFAC situation. If there was a Notary for OFAC enforcement for the US issuing digital court orders for sanctions against Russia and a Notary in Russian issuing digital court orders for sanctions against the USA, how does that resolve? Are we going to end up with USA-chain? BSV not usable in China?  
  
As part of the Blacklist Manager Technical Manual there is a glossary which includes their definition of "Legal Terms" which is, frankly, incredible. This is either terribly sloppy work or is willfully broad, leaving huge grey zones as to what is or is not acceptable to be enforced for freezes or asset reassignments. 



**Could the Tulip Trust Ltd 's legal notice be interpreted as a "Court Order?" Yes.**

**Could a meeting of a bunch of lawyers employed by TTL be interpreted as a "Law Court?" Yes.**

![](/website/assets/images/2022/10/glossary.png)  
  
The miners will do what they are told

Everyone who runs the BSV Node software is doing so under the licensing agreement which accompanies the source code and binary releases of that software.

The licensing for that software changed from an open source license to a proprietary license on [2nd May 2019](https://github.com/bitcoin-sv/bitcoin-sv/commit/e6474ba84db58d8adf01354a8c12931a9d7e8d3d), when the MIT license put in place by Satoshi in the very first release of the Bitcoin source code had a raft of restrictions added to it which mean it no longer meets the [Open Source Definition](https://opensource.org/osd) as maintained by the [Open Source Initiative](https://opensource.org/) non-profit, failing on nearly every point, with the exception of the source code being available.

Here is the key line - [**https://github.com/bitcoin-sv/bitcoin-sv/blob/master/LICENSE#L20**](https://github.com/bitcoin-sv/bitcoin-sv/blob/master/LICENSE#L20)

------------  
`2 - The Software, and any software that is derived from the Software or parts thereof, can only be used on the Bitcoin SV blockchains. The Bitcoin SV blockchains are defined, for purposes of this license, as the Bitcoin blockchain containing block height #556767 with the hash "000000000000000001d956714215d96ffc00e0afda4cd0a96c96f8d802b1662b" and that contains the longest persistent chain of blocks accepted by this Software and which are valid under the rules set forth in the Bitcoin white paper (S. Nakamoto, Bitcoin: A Peer-to-Peer Electronic Cash System, posted online October 2008) and the latest version of this Software available in this repository or another repository designated by Bitcoin Association, as well as the test blockchains that contain the longest persistent chains of blocks accepted by this Software and which are valid under the rules set forth in the Bitcoin whitepaper (S. Nakamoto, Bitcoin: A Peer-to-Peer Electronic Cash System, posted online October 2008) and the latest version of this Software available in this repository, or another repository designated by Bitcoin Association`

------------  


You can only use the software on **the BSV fork of the Bitcoin blockchain** and you are also **compelled to run the latest version of the software**. There are no alternative implementations of the BSV client software, so you are taking whatever changes the maintainers want to make and there is nothing you can do about it. Those changes can include major changes to functionality (like the Blacklist Manager).

The freezing code was added to BSVNode in the 1.0.9 version released in October 2021 so will already be being used by all node operators.  
  


  
OPINION - Why do this? What is the endgame?

So this is all pretty undesirable in the opinion of the author, but what is the big deal? If the only outcome is that the BSV community is so compliant that it allows Craig Wright to reassign Mt Gox coins to himself which he claims were stolen then what is the harm? It it just further proof of cult-like behaviour which won't surprise anybody outside of that bubble. Right? **Wrong.**  
  
Tulip Trust Ltd issued legal notice to **BTC and BCH developers too at the same time** , and will no doubt use a "successful" implementation on BSV to prove that this is possible and that BTC and BCH developers are willfully obstructing legal due process and "law and order" if they do not do the same. Even beyond Bitcoin-family chains, any such precedence puts all blockchain projects and their developers at legal risk

The cover story is of BSV being a "legally friendly" blockchain which protects victims of crime. The reality is a horrific backdoor in the protocol which presents terrible danger of abuse to end-users and goes against the whole "immutable ledger" basis of blockchain.

It is obviously important for blockchain projects to comply to legal requirements in the jurisdictions which they operate, but tools for these purposes are better implemented at a higher level in the stack - not by dangerous intervention on the ledger itself. That approach introduces a subjective mechanism into a system which is very intentionally objective and tamper-resistant.

Law enforcement already have incredible tools to do their job, in the form of an immutable ledger and powerful chain-analysis tools.  
  
The playbook here is very similar to the backdoors proposed in encryption in the 1990s onwards. Backdoors to encryption were largely beaten off because of the risks which they represented to all participants.

In the author's opinion the same fight is required to halt "solutions" which seek to censor or blacklist transactions on blockchains, let alone to reassign coin ownership.  
  
**These blockchain backdoors can and will be abused and are ultimately not in the public interest.**
