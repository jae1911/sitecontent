---
title: "New hosting platform"
date: 2023-01-03
draft: false
---

Today, let's talk about on of my new projects for 2023: migrating hosting to ARM-based computers.  
For now, services (except a few select) are hosted on a bunch of x86-based servers (mainly HPe ProLiant ones bought for cheap online).  
I got some problems with the current infrastructure:
 - Costs a lot to run (mainly in housing and electricity)
 - Is super hard to move (bulk servers that are super heavy)

To solve that, I am currently testing a new solution: running all of the services on ARM-based SBCs.  
For that, meet the Orange Pi 4 LTS.

![Orange Pi 4 LTS single board computer; image is dithered](https://bm.777.tf/wb/pics/sbc-optim-small.jpg)  
(Picture CC 4.0 BY-SA Jae Lo Presti; [click here for  a larger pic](https://bm.777.tf/wb/pics/sbc.jpg))

That particular one has:
 - 4G of RAM
 - x6 ARM CPU cores (Cortex-A72+Cortex™-A53)
 - 16G of EMMC storage
 - Gigabit ethernet

For now, this one only has light web stuff, including the website you are reading right now.  
Services such as the BreezeWiki or AnonymousOverflow will be moved on there soon as a way to test if this exact platform is suitable for larger deployments.

Even tho there has been some problems when switching the website to it, it now runs flawlessly (the website is a bit slower than before but nothing unbearable).  
Some fun experiment that would be fun to do later would be trying to take the whole website off-grid or even better, when moving physical locations, make it so the servers stays up (I will have to make a post detailing more how I could do that).

The current goal isn't to go completely low-tech, *at least yet* but to try new things while trying to save a bit of money.  
As a fun trivia, added the network stats of the machine on [the main page](/) (just scroll down until you see an image with a fancy chart).  
I might do that for every single machine once I start migrating and that data will have its own page in the future.

That's it for the first post of the year and I'll see you next time!

---

If you liked this post, consider adding it to your [RSS](/blog/index.xml) or [JSON](/blog/index.json) feed reader :)
