---
title: "Testing phones I found"
date: 2022-06-01
tags: ["tech"]
---

Hey there!

Recently, I got a hold of some interesting phones so I guess I had to make a small blog post about those.

## Nokia N900

The Nokia N900 is a phone with an integrated physical keyboard and even a stylus that was released in 2009 which was shipped with Maemo 5 back then.

I discovered this device while trying to install Postmarket OS on another and saw the nice support it had.It's only recently that I could buy one for really cheap (around 25€) on the Finnish website Tori (like craigslist but in Finland).

I tested multiple OS on this phone including:

- The default one: Maemo
- A variant: Maemo Leste (which is Open-Source)
- A full-blown Linux: PostmarketOS

Surprisingly, the default OS, despite being from 2009 is still very usable today, however it suffers from being really outdated and having certificate problems.Otherwise, it is still a very potent phone by today's standards.

The only thing to note is that if you plan on running PostmarketOS on it, there is currently no battery protection which is something to keep in mind.

## Unknown (labelled as S22 Ultra; MTK6580_8.1 in reality)

So far, of all the times I ordered on Aliexpress, I never got deceived... until today.

As some background, I recently ordered a 80€ smartphone from Aliexpress, supposedly being a S22 Ultra (yes, you heard it right, like Samsung).For once, the shipping was surprisingly fast, at around two weeks.

Upon unboxing, the phone itself looks pretty nice, you can clearly see it ressembles the Samsung S22 Ultra (on which it is copied).

Hell, it even came with a stylus, headphones and a free case, what a deal!Only problem, upon launching it, I could only notice the cheap "Welcome" text animation that ran somewhere around 2FPS (and I'm pretty generous).

When the interface finally loaded, everything was kinda responsive and looked like Samsung Android. Only problem, this is only a facade, all apps have icons of Samsung apps but are in reality only the Android defaults.

Also, I noticed in the settings that the phone exactly matches the seller's page which means 8GB of Ram and 240GB of rom. Being naturally skeptical, I fired up adb and to my immense surprise, something bad showed up...

What? Have I been lied to??

Sadly yes, this phone is in in reality displays a MTK6580_8.1 in its properties and upon a quick search on the internet, the specs match:

- 16GB ROM
- 2GB RAM

Now comes the case of that "128GB" Micro SD card included as a "gift" with the phone. Formatting the card to ext4 (or any filesystem) would work but mounting it always returns an error which **_may_** **_maybe_** be an indication that the card **_might_** be fake as well (yes it is).

Also, after some time, inspected the multiple cameras at the back. Turns out all of them are fake except the very top one that is the only one that can actually take pictures. I'll see more about that when I'll take all of this apart (maybe for a next blog post 👀).

So, in conclusion, remember two things:

- If you buy a phone for less than 100€, you get what you get for less than 100€: not the latest Samsung but some generic phone that may be just good enough to call and send SMSes but no more
- If something is too good to be true, it's that it's probably the caseAnd that goes not only for Aliexpress but any kind of online store.

Of course, I opened a dispute and given the activity of the seller, I'll probably see my money again in some days (I'll keep you updated for that).

That's all for today's post, have a great pride month and I'll see you next time!
