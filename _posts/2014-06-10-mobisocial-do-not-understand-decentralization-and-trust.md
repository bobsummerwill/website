---
layout: post
title: "MobiSocial do not understand decentralization and trust"
date: "2014-06-10 16:14:59 -0700"
permalink: /2014/06/10/mobisocial-do-not-understand-decentralization-and-trust/
---

**UPDATE: My[tweet](https://twitter.com/BobSummerwill/status/476514451902828544) of this blog entry got a couple of brief replies from [Monica Lam](http://suif.stanford.edu/~lam/), and I piled on some further criticism.**

* * *

One of the keynote speeches at the recent [Tizen Developer Conference 2014](https://www.tizen.org//events/tizen-developer-conference/2014) was given by [Monica Lam](http://suif.stanford.edu/~lam/) of [MobiSocial](http://www.mobisocial.us/about/), presenting their [Omlet chat platform](http://www.omlet.me).

![](/assets/images/2016/06/Omlet.png)

I was interested to hear what they had to say, because I have been following "BitCoin 2.0" technology recently. I am specifically interested in the paradigm-shifting consequences of truly trust-less distributed ledger systems like the [Bitcoin block-chain](https://en.bitcoin.it/wiki/Block_chain) and other distributed consensus systems, such [as the one used by Ripple](https://ripple.com/wiki/Consensus).

I'm sad to report that despite [MobiSocial](http://www.mobisocial.us/about/)'s obviously good intentions, they have built a system which still operates within the old paradigm. They have just inserted themselves in place of the existing status quo (whether Facebook, Google, Microsoft or Apple).

Installing [Omlet Chat](https://play.google.com/store/apps/details?id=mobisocial.omlet) from the [Google Play](https://play.google.com/) store brings up this horrifying list of required permissions:

     * In-app purchases
     * Cellular data settings
     * Identity
     * Contacts/Calendar
     * Location
     * SMS
     * Photos/Media/Files
     * Camera/Microphone
     * Wi-Fi connection information
     * Device ID & call information
     * Other (access Google photos)

Wow! So I shouldn't trust first parties, but I should give [MobiSocial](http://www.mobisocial.us/about/) the keys to the palace?

OK, but this is just for the client-app on device, right? After that it is all peer-to-peer, right? That's what is new here, right? Wrong.

There is still a very strong dependency onto a single point of failure - the [MobiSocial](http://www.mobisocial.us/about/) servers, which seemingly hold TONS of private information on you … <http://omlet.me/legal/privacy-android.html>.

If you want to develop an application for [Omlet platform](http://www.omlet.me) then you need to register your application with them - <http://www.omlet.me/docs/> - presumably again so that information on it can be stored on their server.

It appears to me that [MobiSocial](http://www.mobisocial.us/about/) do not truly understand decentralization and trust. They just want to build another platform, which THEY control (and can monetize). Promising that you don't intend to commercialize private data isn't good enough. We need trust-less systems which guarantee that the participants **CANNOT BE EVIL** , because there is no platform-holder, bank, exchange or other single point of failure on which unconditional trust is required.

It is good that [Omlet](http://www.omlet.me) does not store your data, but it still stores rafts of metadata on their servers. Also, ask yourself if moving your data from Apple/Google to Dropbox is really a big win.

Check out some of these projects if you really want to keep your data private:

     * [BitMessage](https://bitmessage.org) - Bitmessage is a P2P communications protocol used to send encrypted messages to another person or to many subscribers. It is decentralized and trustless, meaning that you need-not inherently trust any entities like root certificate authorities.
     * [BitTorrent](http://www.bittorrent.com) - Delivering an Internet of Options, Not Rules.
     * [BitTorrentSync](http://www.bittorrent.com/sync) - BitTorrent Sync lets you sync and share files and folders between devices, friends, and coworkers.
     * [PGP](http://en.wikipedia.org/wiki/Pretty_Good_Privacy) - Pretty Good Privacy (PGP) is a data encryption and decryption computer program that provides cryptographic privacy and authentication for data communication.
     * [Tor](https://www.torproject.org/) - Protect your privacy. Defend yourself against network surveillance and traffic analysis.
     * [Tor Browser Bundle](https://www.torproject.org/projects/torbrowser.html.en) - The Tor Browser Bundle lets you use Tor on Windows, Mac OS X, or Linux without needing to install any software.
     * [Orbot](https://guardianproject.info/apps/orbot/) - Orbot is the safest way to use the Internet on Android. Period.
     * [Tails](https://tails.boum.org/) - Tails is a live operating system, that you can start on almost any computer from a DVD, USB stick, or SD card.
     * [MaidSafe](http://maidsafe.net/) - MaidSafe is a fully decentralized platform on which application developers can build decentralized applications.

I have uninstalled Omlet from my Galaxy S4 and my Samsung Gear 2. If you care about your data privacy, I would recommend that you do the same.
