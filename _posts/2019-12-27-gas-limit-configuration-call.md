---
layout: post
title: "Gas Limit Configuration Call"
date: "2019-12-27 06:47:58 -0800"
permalink: /2019/12/27/gas-limit-configuration-call/
featured_image: /assets/images/2019/12/conferencecallphone.jpg
---
![img 20180801 122417](/assets/images/2018/08/img_20180801_122417.jpg)



We just had an [ETC Devs / Miners / Community call](<https://github.com/ethereumclassic/ECIPs/issues/252>) to talk about options to manage rampant chain bloat we are seeing on the ETC mainnet which is being caused by [GasToken](<https://gastoken.io/>), with most blocks being filled with garbage, adding gigabytes to the state every day. This will compromise decentralization in short order and is an existential threat to the health of the network.

Here is a copy of the [recording of the call](<https://bobsummerwill.wordpress.com/wp-content/uploads/2019/12/192712-etc_gas-limit-configuration-call_discord.mp3>). Thanks to a.s. for that.

My suggested ACTIONS ITEMS:

  1. Blog post on <https://ethereumclassic.org/> by @zacmitton explaining the situation and appealing to miners to voluntarily reduce gaslimit. To 1M? To 2M? To 4M?
  2. Outreach on the above (using existing contacts we have used for prior HFs)
  3. Volunteers to generate pull-requests against Parity-Ethereum, Geth Classic, MultiGeth and Hyperledger Besu which change the defaults for ETC to the same.
  4. Volunteers to consider countermeasures to reverse as much of the damage-to-date as we can by buying gastokens (using community fund if this is expensive) and then using them to debloat the chain.
  5. Volunteers to consider protocol changes for the long-term, which could include: 
     1. Gas price changes
     2. Removing opcodes (remove refund opcode, remove selfdestruct)
     3. Hard cap gas and curve (my pending ECIP) to give multi-decade certainty.



Future discussion is best done on [Github issues within the ECIP process](<https://github.com/ethereumclassic/ECIPs/issues>), for global visibility and permanent papertrail on the decision-making process.

Thanks to Zac Mitton for setting up and hosting the meeting.
