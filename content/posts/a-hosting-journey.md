+++
date = '2025-08-01T16:04:53-04:00'
draft = false
title = 'A Hosting Journey'
tags = ['infra', 'networking']
+++

## TL;DR
For those who like brevity, sometimes you just need to sit down and do something. A project may just be held back because you are getting stuck at square one. This site has been delayed not once, not twice, but probably 3-4 times now as school got busy, then work got busy, then school, then... Truth is life is busy and personal projects won't do themselves. 

Make time for the projects you are interested in pursuing. Take time to start. Sometimes once it is started, its not so bad after all. Lastly, learn from what challenges come along the way. Perhaps you will discover a new way to approach that next project or do things differently to manage your time.

## A long awaited blog
In college, some friends of mine introduced me to the joy of surfing the internet for interesting cyber blogs. Some of my friends even had blogs where they would share topics. So, naturally, I started to find them interesting and often wanted ways to easily share findings and information among friends or even to note down how a process worked for myself. So I started to set out on a journey exploring how to run a website.

There are lots of options. I like to simplify it down to two paths: those who like javascript and those who don't. I didn't realize this until later down the road (you'll see), but many modern websites seem to have developed into quite heavy full stack javascript applications. At first it seems rather natural to try and build a custom site from total scratch! Easy right? Just load up `nodejs` with some `npm` packages, write an `expressjs` router config for the different paths, template out a few pages with `ejs` and now it is off and running. This is great and all... until I realized that a comments form that renders to the page now allows for XSS because I forgot to sanitize input. Now time is getting spent trying to make sure any site interactions are sanitized and less focus is getting put into the content. Also, I realized how much I didn't really enjoy writing CSS and all the HTML boilerplate to get things moving faster. But, I wouldn't have known these things and where my interests lie had I not tried this. So where to go from here.

Enter Flask. For a short period of time, I convinced myself it was just that I didn't really like writing javascript apps so I turned to a language I am more fluent in: `python3`. Well, that was short lived as well. What I learned was that I don't want to get so caught up in the structure behind how my website works that I don't actually produce a website. But an idea that came from when I was working on the flask backend for that short time was if I could use markdown as how I write content, and then render it to the pages I want. Well, a quick survey of prior work led me to [Hugo](https://gohugo.io/) which has been achieving this for a while now.

So that settles it. I now have a way to write and put my thoughts on a reasonable looking website without getting so caught up in what it could do. Also I didn't have to mess with CSS `flexbox` properties for hours to get just the right shape to things on my page. Several blockers are now gone, so lastly is hosting. As life has currently entailed a lot of moving and relatively short durations in places, I don't have a homelab with good uptime. But nevertheless tried a few things out before settling on my current choice.

Although I can't speak for those who are die hard Apache web server people, I just can't find a good reason to enjoy it. In my experience the config files are often quite large by default and trying to make sure any additional mods are installed an running can take time, and it just seems complicated starting out. Nginx on the other hand is fast and simple to get working. The configuration files are small. The settings are quick and easy to change. And it can do some very neat stream proxying too! [See source](http://nginx.org/en/docs/stream/ngx_stream_proxy_module.html). Now the last piece is just getting out to the world. For this, I wanted to use [Cloudflare's Zerotrust tunnels](https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/). This actually works quite slick for hosting without a public IP or portforwarding. This worked for a while (To my point earlier that personal hosting is not quite there yet) until I unplugged my pi hosting my site as I was moving and forgot to put it back up when I got settled in. 

So alas, I thought I was maybe just gonna have to deal with some poor uptime, but from a mention of a friend I discovered [Cloudflare pages](https://developers.cloudflare.com/pages/)! As long as you have a static content site (check! Hugo makes static sites!) it can be deployed starting for free! At this point I find their free tier to be quite enough to get started and think that will likely be the case for a while.

To the old saying:
> Its the journey, not the destination

This has been a very good time of exploring and learning to get here. It could have been much shorter, but sometimes life gets busy and in the way of non-pressing issues. Maybe sometime down the road this site will be more handcrafted. Time will tell.
