---
layout: post
title: "Why I will probably refuse your meeting request and not answer my phone"
date: "2015-07-24 08:23:58 -0700"
permalink: /2015/07/24/why-i-will-probably-refuse-your-meeting-request-and-not-answer-my-phone/
categories:
  - "Uncategorized"
---

If you are a geek like me, you will have a good understanding of [synchronous versus asynchronous](<http://stackoverflow.com/questions/748175/asynchronous-vs-synchronous-execution-what-does-it-really-mean>) operations.

[![120301](/assets/images/120301.gif)](</assets/images/120301.gif>)

When most computers were only single-threaded with one CPU core there was little need for asynchronous operations. You would have queues and stacks for deferred work, but all operations were essentially gated by the total volume of work to be done. You could use data structures to change the order in which that work happened, but there was no potential for truly parallel work.

In my [undergraduate Computer Science course in Leeds, UK](<http://www.engineering.leeds.ac.uk/computing/>), from 1993-1996 one of our text books was [Ben-Ari's Principles of Concurrent and Distributed Programming (1990)](<https://www.chapters.indigo.ca/en-ca/books/principles-of-concurrent-and-distributed/9780321312839-item.html>) which covered the primitives which you need to introduce when you have more than a single thread, or for inter-process communication, or for multiple cores, or for multiple networked computers.

Anybody who has been through such a course will remember [The Mutual Exclusion Problem](<https://en.wikipedia.org/wiki/Mutual_exclusion>) and [The Dining Philosophers Problem](<https://en.wikipedia.org/wiki/Dining_philosophers_problem>) (both first noted by [Edsger W. Dijkstra](<https://en.wikipedia.org/wiki/Edsger_W._Dijkstra>) in 1965. **That is 50 years ago**), semaphores and mutexes. Our exercises at the time were on [Transputers](<https://en.wikipedia.org/wiki/Transputer>) using [Occam2](<https://en.wikipedia.org/wiki/Occam_\(programming_language\)>). Those technologies are the ancestors of [Clojure](<https://en.wikipedia.org/wiki/Clojure>), [Erlang](<https://en.wikipedia.org/wiki/Erlang_\(programming_language\)>), [Rust](<https://en.wikipedia.org/wiki/Rust_\(programming_language\)>), [Scala](<https://en.wikipedia.org/wiki/Scala_\(programming_language\)>) and [Stackless Python](<https://en.wikipedia.org/wiki/Stackless_Python>).

[![20150724_105245](/assets/images/20150724_105245.jpg)](</assets/images/20150724_105245.jpg>)

Well guess what? Our work "work streams" suffer from exactly the same concurrency problems as computers, because these patterns are the nature of the beast for any coordinated activities, whether that is in digital form for computers or in organization form for team activities within corporations.

Phone calls and meetings are synchronous operations. They force everyone involved to stop and wait for each other. If unplanned they are [preempting](<https://en.wikipedia.org/wiki/Preemption_\(computing\)>) the other person's priorities and causing a context switch. Flow is broken. The most important work which the other person was focusing on just got bumped.

Synchronous operations ruin parallelism and overall organization efficiency. They force people into a "waiting" state at a frequency which is really unhealthy. If you allow other people to preempt your priorities all of the time then you are not driving your own priorities. You are allowing other people to "override" you constantly. We see this anti-pattern commonly with phone calls in shops. Somebody is helping you and then the phone rings and they "put you on hold" to answer the call. Well hello! I am right here, ready to buy something. You just bumped me for some random phone call which may or may not be important. That isn't very nice. In the same way, constantly monitoring e-mail is a similar pattern. You are saying "Responding quickly to anybody who happens to send me an e-mail is more important than anything else I might currently be working on".

Most people have probably seen this quadrant. Repeated allowing unplanned synchronous tasks into your daily workflow traps you in quadrants Q3 and Q4.

**So … if I don't answer your call, or reject your meeting request, please don't be offended! Send me an e-mail or IM message (Lync, Twitter, Telegram, Hangouts) and I will get back to you asynchronously. I suggest that you consider doing the same yourself 🙂**

[![MerrillCoveyMatrix](/assets/images/merrillcoveymatrix.png)](</assets/images/merrillcoveymatrix.png>)

From <https://en.wikipedia.org/wiki/First_Things_First_(book)#/media/File:MerrillCoveyMatrix.png>
