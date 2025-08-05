+++
date = '2025-08-05T14:00:54-04:00'
draft = false
title = 'DakotaCon Cyber Conquest - Third Year in Review'
tags = ['projects', 'infra', 'competition']
+++

{{< figure src="/images/dakotacon_cyberconquest_logo.png" width="400">}} 

## Open thoughts first.
It was a good year. Had some fun with the variety of physical systems, got stressed with the deadlines as usual. Shared some great laughs, some tears, but most importantly had the joys of good camaraderie, great friendship, perseverance, and the deep satisfaction of seeing things through to the end. 

Had an awesome time debugging and troubleshooting the Ubuntu failure after comp start. Initially thought that some configuration I had made causes stability issues but learned that it was purely a team's broken implanted PAM backdoor. The sleep-deprived high that came from going through logs for hours, testing several possibilities, deducing further issues or possible causes, and finally nailing the root cause and quick evaluation leading to a source of the attack was just amazing. Ethan did an amazing debrief about how bad this PAM backdoor was, see [this video](https://www.youtube.com/live/NOx8F_Gr8ps?feature=shared&t=1041).

The long night with setup and sleeplessness made for one heck of a day. Drowsy, but vibing on the good times, 2 cups of coffee, and pure adrenaline meant that I was just taking the day in stride, fearlessly and boldly enjoying the efforts of hard labor. Brandon's reality chicken made for some of the best laughs and much need comic relief throughout it all. To end the day with some food, drinks, laughs, and fun later was also so refreshing. The sleep you get from pulling an all-nighter is wild. I felt like I was asleep for like a week and woke up half dead. 

{{< figure src="/images/reality_chicken.jpg" title="reality chicken... for a good laugh at 3am" width="200" >}}

Life is short, Laughter and friendship make it all worth it. The hard-earned joys last the longest, and a few sleepless nights are ones you remember forever.

Kudos and love to my wonderful teammates, friends, and persistent survivors of the endeavor. Thank you all for making this whole thing worth it. I have so much fun working alongside you all and appreciate you sticking through to see the end. And thanks Brandon for the reality chicken, it really helped keep the spirits up and added a good laugh.

## What is DakotaCon Cyber Conquest?
For context, [DakotaCon](https://dakotacon.org/) is Dakota State University's (DSU) cyber security conference. Starting back 3 years ago, [a friend of mine](https://blog.gael.in/cyberconquest) and I had an idea to bring a hands-on activity to this conference that was free for anyone (rather than just paid trainings). So, we set out to build a competition that featured a mock smart city of various components (from Raspberry Pis to USB breakout boards). Each team that plays earns points through keeping their city functional while also hacking into other teams to plant persistence and earn additional red team points. 

{{< figure src="/images/cyberconquest2023-laptop.jpg" width="500" >}}

First year was a little rocky to get going (4 core team members over the span of roughly 2.5 months trying to build our first cyber physical competition), but it happened and people gave us good feedback and overall enjoyed the style. Second year went a little smoother; we were able to develop physical systems better, design an actual cityscape to set the theme, improve some of the virtual to physical scoring capabilities, and even have an amazing 'highway' system thanks to Gaelin. Much of this was possible due to the help from a larger team that eased the challenges of development (all of us are volunteer and mostly full-time students). This past year we had what was likely our best year yet (aside from a few speedbumps I'll discuss shortly). We were able to get some new physical systems configured, a live LED scoreboard of team statuses, and even our first attempt at a wireless service!

Here is a short list of all physical services we have made to date:
- 2023
  - Water tower (yes... there was water, and a few close calls)
  - Traffic Light version 1 
  - Wind Turbine
- 2024
  - Traffic lights version 2
  - Cranes
- 2025
  - Drawbridge
  - Cranes
  - Traffic lights version 3
  - Billboard
  - Radio tower
  - LED Scoreboard (White team)

Each year we have tried to refine the overall experience while also adding or improving the physical services. We have gotten a chance to work on some neat experiments as we try to create an aesthetic experience with good functionality. Some of our most interesting projects include working with [this cute little SPI display](https://www.adafruit.com/product/3533), a [general purpose multiprotocol breakout board](https://www.adafruit.com/product/2264), an [even smaller multiprotocol board](https://www.adafruit.com/product/4471), and [even some servo motors](https://www.adafruit.com/product/169). The fun that comes from trying to make physical systems work well in the competition gives us all a chance to experiment and apply our skills to something new!

## Notable mentions:
While this third year somehow took longer to setup than the second year (had everything set around 7am...), there are several things we greatly improved on from prior pitfalls. Some issues corrected were:
- running the DC on a laptop (where any problematic configuration cannot quickly be redeployed) and instead hosting it virtually
- Correcting the HRM stuff with an alternative (MintHCM > OrangeHRM)
- We led working meetings that were significantly more productive. This helped us keep on track better than last year (can still get better, but this was a needed improvement)
- We improved source code management and had most code in GitHub from the start of development instead of an afterthought
- We got all Fujitsu laptops that simplified network configurations per team (allowing all laptops to be hardwired)
- We had an attempt at a wireless service (had been a wish from years prior), and the PoC worked, even if we couldn't get scoring in time
- We improved the vulns baked into custom services allowing for more interesting interactions.
- We greatly improved our marketing, our registration signups, and our admin details for when a competitor entered the room.
- We had awesome things designed to add depth to competitor experience:
	- Live scoreboard posters
	- Medals (take 2) (Thanks Brandon!)
	- Awesome custom logo and packet (thanks to Gillian!)
	- Improved the introduction, team systems, and breakdown of how the competition works morning of with a quick PSA 

## Considerations for future!
Most of the developments this year (aside from last week of prep and deployment) were definitely better than years previous. We made some bumps in the road from not testing at scale and having a clear parts order to request from people. But custom services were designed out faster and boxes built quicker (I think) to the point where we had cloned laptops well in advance to week of (barring the Raspberry pi). 

So a short list of things to consider for this coming year:
- Have prototypes working before Winter break, leaving plenty of time for parts orders and testing at scale
- Keep services simple in design, add fun/extra functionality after it works
- Setup day needs better planning and clearer guidance. Several of us members on the core team got a little lost in configuration steps that should be offloaded to an able hand to better prioritize tasking.
- Different passwords for teams (Little more work on our part, but prevents minute zero scripting).
- Documentation (On box building, on source code, on how a system works and all dependencies)

### Documentation 
Seems like one of our largest issues is purely documentation.
- The Roadmap :TM:
	- Part of the reason things take longer to layout and setup or build out is a lack of shared vision across the team. While someone making something may have a great idea, it's not very actionable without clear communicated goals, steps to reproduce, part lists, wiring diagrams, etc.
- The answer key :TM:
	- Boxes should have short write-ups rather than just a spreadsheet with a handful of lists. We really didn't do a good job at keeping the list updated aside from essential networking details. Without a clear idea of what each system was scored on or what was vulnerable, it is unclear if it is finished, or needs more work. Furthermore, it means that we can't provide a clear "debrief" to our competitors because we need each team member present to discuss a system (and that rarely is the case)

Shortcomings in documentation lead to a fractured understanding of our own environment. Consider a few things:
- roughly 2 people were the only ones who understand the Radio service
- 1 person was the primary person who understands how setup and operations of the Cups service worked for the billboard
- For a time, only 1 member understood how the drawbridge worked until some code inspection happened with a team member and I to understand what caused it to lift
With our simple services having a low team comprehension, it is easy to lose track of how things work, where things go, and more importantly how to fix them or test/troubleshoot when things go wrong during setup.

Lack of parts lists and setup/wiring diagrams meant that most systems could only be configured slowly by knowledgeable individuals until a clear PoC existed for people to replicate. And to the parts list point, we need to create team wide Bill Of Materials. Anything and everything that a team needs should have a count. Number of ethernet wires, laptops, switches. Further, number of Arduinos, type and count of jumperwires per configuration, etc. Without a clear and succinct list of materials, we are certainly going to run into the exact same issues and deadlock of acquiring parts that we did this year (And the sooner we have this, the better off we are in case we need to order a new shipment). Big thanks to Tom for all his help retrieving materials. 

### Box Building
There appeared to be a few notable dilemmas in this year's systems
- DC fell off the domain (yep... I am not a Windows guy, so I can't explain)
- Windows systems had some flaky logins on competition day when Echo-Solis didn't seem to have the userlist (anecdote)
- Ubuntu 16.04 is not ideal for custom services due to out of date packages and dependency issues trying to upgrade things. This caused some problems when trying to pivot the Traffic light service away from RPi to a FT232H breakout board. 

While it is fun to have old systems for the vulnerabilities, considerations should probably be taken into account for system stability and flexibility when pivoting custom services. We could have identified these problems earlier if our development had been slightly more on time but to a stronger point more comprehensive. To that note, quality and stability testing of environment should happen as soon as possible to ensure on time delivery of all custom services and more importantly time to add scoring engine custom builds.

### Testing
Some of the delays and issues discovered night of and night before should have been found, troubleshooted, corrected or mitigated well in advance to go time. I think time target should be to have a batch test 1 month prior to comp to allow time for any additional part orders, grace time with laptop cloning, and otherwise time to correct and issues before large scale development.

### Parts
Seems that although we ordered parts WELL in advance after last year's retro, we could still use:
- More LED strip lights for roads (because somehow 2-3 reels have disappeared)
- Probably could use some more jumper wires? Seems like many of the builds this year were wire hungry
	- Especially female-male ones since some were coming off of headers on a chip and getting pressed into a breadboard.

### Scoring
I know we have considered the flaws in scoring in the past, but we may need to further consider them again and try adjusting weights. For one, scoring strongly favors red team points, especially given that creds are shared across teams. Fixes:
- Balance points better between blue team/red team activities
- Make a short 5-10 min truce at beginning to allow for some initial hardening to occur?
- Don't make each team with same creds?

We did theoretically fix the precompiled binaries for people to pull from [defsec.club/callbacks](https://defsec.club/callbacks) to hopefully have easy drop ins.

## Unsolicited thoughts
Some neat ideas for reproducibility and also further deliverables for other schools or competitions could be:
- Well documented box building guides/ walkthroughs
- Dockerized services for anything custom to be able to deliver quickly to other systems or competitions
- Thanks to Brandon for the consideration of possibly ironing out an elective type course material on how to develop a competition like this (practical skills relating to system administration, software development, and dev ops style delivery)
- Possibly making this into a competition as a service? Could be fun but also means we need to iron out creation, testing, and deployment.

## Fun ideas
- Quotes channel for the team bloopers that were sooo good this past year. Man, the laughs were so satisfying from some of the setup moments

## Thanks
Shout out to the faculty and staff team for all their help
- Tom for all the help with materials
- Kyle for coordinating us with the conference
- Eric for helping with all our networking needs

{{< figure src="/images/cyberconquest2025-setup.jpg" title="core team at 7am after setting up all night" width="500" >}}
The lead admins for their reliable support and efforts to put this together in many capacities
- Brandon
- Gaelin
- Gillian
- Irina

{{< figure src="/images/cyberconquest2025-team.jpg" title="The ops team!" width="500" >}}
And everyone else who made this possible
- Benjamin (on Crane design)
- Brayden (on Linux)
- Collin (on Crane and Drawbridge)
- Ethan  (on billboard and much help with other Linux systems)
- John  (on wireless)
- Kalen  (Windows box building)
- Liberty (Thanks for the photos! and on Drawbridge)
- Malachi (on Windows)
- Rayn   (on Windows)
- Will   (on Crane)
