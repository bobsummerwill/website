---
layout: post
title: "DevOps Days Toronto – Day 1"
date: "2015-05-14 20:44:30 -0700"
permalink: /2015/05/14/devops-days-toronto-day-1/
---

Bob Summerwill, Steve Henry and Stephane Matis attended the first day of [DevOps Days Toronto](<http://www.devopsdays.org/events/2015-toronto/> "DevOps Days Toronto") today. You can follow along at [@DevOpsDaysTO](<https://twitter.com/DevOpsDaysTO> "@DevOpsDaysTO") on Twitter.

It's a lot bigger than I expected, with around 350 attendees, up from about 180 last year, with many attendees from out of town. There is lots of cross over with the [DevOpsTO Meetup](<http://www.meetup.com/DevOpsTO/> "DevOpsTO") group. [Steve Pereira (@SteveElsewhere)](<https://twitter.com/SteveElsewhere> "Steve Pereria \(@SteveElsewhere\)") is the primary organizer of both.

The event is being held in the Glenn Gould Studio at the CBC Broadcast Centre on Front Street.

[![2015-05-14 12.55.08](/website/assets/images/2015/05/2015-05-14-12-55-08.jpg)](/website/assets/images/2015/05/2015-05-14-12-55-08.jpg)

[![2015-05-14 12.55.00](/website/assets/images/2015/05/2015-05-14-12-55-00.jpg)](/website/assets/images/2015/05/2015-05-14-12-55-00.jpg)

 

The area with the vendor booths was really busy at the start of the day, with a good range of companies represented:

  * VictorOps
  * Sonatype
  * B Pespectives
  * VM Farms
  * Shopify
  * Ansible
  * PagerDuty
  * Puppet
  * Microsoft
  * IBM
  * Chef
  * Shomi
  * New Relic
  * HP



[![2015-05-14 12.55.57](/website/assets/images/2015/05/2015-05-14-12-55-57.jpg)](/website/assets/images/2015/05/2015-05-14-12-55-57.jpg)

[![2015-05-14 12.56.19](/website/assets/images/2015/05/2015-05-14-12-56-19.jpg)](/website/assets/images/2015/05/2015-05-14-12-56-19.jpg)

[![2015-05-14 12.56.06](/website/assets/images/2015/05/2015-05-14-12-56-06.jpg)](/website/assets/images/2015/05/2015-05-14-12-56-06.jpg)

Bob had to head out of the conference for the morning sessions, but thankfully the sessions were all recorded and uploaded to YouTube on the same day, so here is the keynote, by J. Paul Reed ([@SoberBuildEng](https://twitter.com/SoberBuildEng)), titled "Hacking the CxO Code", with some good tips on framing DevOps for an executive audience. ([Link to YouTube](https://youtu.be/9jKEYB4cvG4?t=18m20s)) - starting @ 18m 20s.

Next up was H. "Waldo" Grunenwald ([@gwaldo](http://twitter.com/gwaldo)), presenting "Agent of Change - Here's Your Helmet" ([Link to YouTube](https://youtu.be/9jKEYB4cvG4?t=59m25s)) - starting @ 59m 25s.

And the third presentation was by Arthur Maltson ([@amaltson](http://twitter.com/amaltson) with "Chef, test-kitchen, Docker, CI, Oh My!". ([Link to YouTube](https://www.youtube.com/watch?v=9jKEYB4cvG4&feature=youtu.be&t=1h43m0s)) - starting @ 1h 43m.

Arthur's presentation was right up my street, walking through behaviour driven testing for server infrastructure using [ServerSpec](http://serverspec.org/) (an extension of [RSpec](http://rspec.info/)) to provide English-language executable tests written in [Cucumber](https://cucumber.io/). Those are driving the execution of command-lines on the machines, via SSH, WinRM, Docker API, etc. All of this was sitting inside [Test Kitchen](http://kitchen.ci/).

Live coding is nearly always very watchable, and that was certainly the case here. Great work, Arthur.

A new unit of server load measurement was introduced in one of the Ignite talks - **Bieberbits** - which is server load as a result of Justin Bieber tweeting a link to your site! Their site spiked at 3.71 Bieberbits during the awards show.

[![2015-05-14 13.28.11](/website/assets/images/2015/05/2015-05-14-13-28-11.jpg)](/website/assets/images/2015/05/2015-05-14-13-28-11.jpg)

The afternoon was run in a different format called Open Spaces, where the participants choose and vote on what they want to talk about for the rest of the afternoon. That was split into 3 sessions slots, with around 7 parallel sessions running in each of those slots. Much like the "birds of a feather" concept, but with the topics chosen on the spot. Anybody could come up to the stage and give a one-sentence pitch for their topic, and the topics with most interest went ahead.

I attended the ChatOps session first, which was ram-packed with attendees. [What is ChatOps?](<http://www.pagerduty.com/blog/what-is-chatops> "What is ChatOps?") I wasn't aware of what ChatOps referred to prior to this session, though I had seen some of its elements before. Essentially, it involves having everyone do their communications within a chat platform, like [Slack](<http://slack.com> "Slack") or [HipChat](<https://www.hipchat.com/> "HipChat"), and then augmenting that setup with bots, which can post into that chat platform, and act based on commands given to them in that same platform. The bots can replace humans doing repetitive tasks, and provide a form of documentation of particular processes. It is very interesting and powerful approach, and it looks like HipChat is available for private installations, and I definitely want to look into that.

[![2015-05-14 14.44.30](/website/assets/images/2015/05/2015-05-14-14-44-30.jpg)](/website/assets/images/2015/05/2015-05-14-14-44-30.jpg)

[![2015-05-14 15.12.03](/website/assets/images/2015/05/2015-05-14-15-12-03.jpg)](/website/assets/images/2015/05/2015-05-14-15-12-03.jpg)

In the second Open Space slot, I attended a session talking about migrating from a traditional development model to a DevOps approach. Lots of war stories in that session. Lots of individuals having to fight "the system" and the DevOps transformation being a long and painful road if there isn't executive buy-in. The third session was about how to sell technical debt replacement. A very tricky proposition.

[![2015-05-14 16.12.44](/website/assets/images/2015/05/2015-05-14-16-12-44.jpg)](/website/assets/images/2015/05/2015-05-14-16-12-44.jpg)

At the end of the day there was a Happy Hour (and a bit), and the rather interesting "Ignite Karaoke". The Ignite format was also used earlier in the day, and consists of slide decks which are auto-advancing each 15 seconds. The Karaoke format had some brave souls (myself included) talking to a set of slides which you have never seen before, and trying to say something cohesive, or funny or both about them.

![](/website/assets/images/external/twitter/CFAKEIiWIAANTr0.jpg)

See [Twitter posting.](https://twitter.com/jasonhand/status/598989820325732352/photo/1)

Had some great chats with many people, and really looking forward to tomorrow!
