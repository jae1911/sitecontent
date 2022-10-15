---
title: "What About Bsd?"
date: 2020-05-30T21:33:43+02:00
draft: false
description: "Using a BSD-based system? Why not?"
---

Greetings everyone, today I'm gonna talk about BSD and my experience with it. If you haven't heard of BSD, I would suggest to read the [Wikipedia article](https://en.wikipedia.org/wiki/Berkeley_Software_Distribution) and then come back.

I discovered BSD few times ago when I was looking for a Systemd-free distro (essentially to test the alternatives, I have nothing against Systemd to be honest), on a forum, someone was suggesting switching to BSD which is not even a Linux distro.  
Curious about this new thing, I downloaded [FreeBSD](https://freebsd.org/) as a test and installed it on my old laptop.  
While this was a fairly old laptop (about 750Mb of ram, an old AMD CPU & GPU and a 65Gb hard-drive), FreeBSD ran smoothly and I though it could be a good idea for my main desktop which at the time was a Dell T3500 Workstation.  
At first, it seemed to be a good idea: it looked just like Linux which I was using for quite some years and most importantly, my GPU (a Nvidia 750Ti at the time) had an official driver made by Nvidia which was somewhat attractive.  
My first FreeBSD installation took hours, simply because I was in an old building served by an old ADSL line, at the time, getting 1Mb/s was pure miracle.  

At first, everything seemed nice, it was working.  
I had what I asked for: a simple desktop environment, a web browser and an IRC client to talk with my friends.  
Then, few days after the initial installation, one problem became apparent: the software support.  
I struggled to find software and getting it to work, while most software usually supports Window, Mac and *sometimes* Linux, finding native BSD programs was almost impossible, at the time, I was using Skype to communicate with class friends or Teamspeak for some games.  
While there were ports of programs from Linux, for some reason, theses didn't worked and just plainly displayed compilation errors.  
This is what made me give up and get back to my Linux (Arch to be more precise).

A little while ago, I re-discovered BSD on the subreddit `r/UsabilityPorn` which featured a extra good-looking BSD build.  
After some time of research and testing, I decided to install FreeBSD on my desktop computer which is now definitely more powerful than my old one.  
As always, the installation went smoothly but when trying to launch a desktop environment, one problem became apparent: my video card wasn't (and is not) supported by FreeBSD.  
Hopefully, after some research, I found a [forum post](https://hardforum.com/threads/freebsd-12-1-and-amd-rx590-setup.1993450/) that explained how to install the `amdgpu` driver for the latest AMD GPUs and which worked fine.  
Hooray, I could now use XFCE4 as a desktop, but wait, what about the software?  
As said earlier, for me BSD has really restricted software which you can run on this system but this time, I wasn't done, I learned how to use ports and for once, it worked!

Usually, the first thing I do when installing a new system is installing the Minecraft launcher and trying to play.  
I saw that FreeBSD has a port named `games/minecraft-client` and then installed it.  
To my surprise, it worked. Not only I could play Minecraft on FreeBSD but also, I could now access a really big library of apps ported from Linux which is very exiting.  

Now that I have this system, I'll use it as my daily driver and post follow-ups to tell what I think about BSD after some usage.

If you liked this article, please consider subscribing through RSS so you won't miss any articles.  
I'll see you next time!
