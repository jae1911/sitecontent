---
date: '2023-10-21'
title: 'You Vs Google ads'
draft: false
---

Hey there!  
If you've been remotely on the internet recently, you've noticed that YouTube
started cracking down on content blockers that happen to block *ads*.

Worry not, I come bearing solutions for this problem (solutions which were
already widespread as soon as the restriction was put in place, but honestly,
this is my blog, what you're gonna do hahahahaah, you can't stop me).

## Solution 1: use an alternative front-end or app

This might be the most radical solution, but the best one: switch to an
alternative front-end.  
Most, if not all, alternative front-ends for YouTube directly remove ads,
trackers and some of them even support the likes of SponsorBlock.

Here are some recommendations (the software with a ⭐ are my personal
recommendations).

### On the web

- ⭐ [Piped](https://piped.video/trending) - An alternative front-end based on
the NewPipe Extractor, implementing SponsorBlock and can bypass *most*
geo-restrictions
- [Invidious](https://docs.invidious.io/instances/) - An alternative front-end
that removes ads, trackers and that doesn't requires JavaScript (if you're that
type of person)

### On your phone

#### Android

- ⭐ [NewPipe](https://newpipe.net/) - The most well-known YouTube client for
Android, being extremely light and even allowing to download videos!
- [LibreTube](https://libretube.dev/) - Modern-looking YouTube client relying
on the Piped API to playback videos 

#### iOS

- ⭐ [Yattee](https://github.com/yattee/yattee) - Piped/Invidious client for
iOS, also has SponsorBlock support

### On your PC

- [FreeTube](https://freetubeapp.io/) - A desktop YouTube client available on
Linux, Windows and MacOS
- ⭐⭐⭐ [yt-dlp](https://github.com/yt-dlp/yt-dlp) - A must-have on any system, a
command-line utility allowing you to download videos and audio from not only
YouTube, but also from a wide variety of websites and platforms

## Solution 2: but I still want to use the official YouTube front-end

For this, just follow those simple steps:
1. Make sure you have [uBlock Origin](https://github.com/gorhill/uBlock)
installed on your browser (it will even improve your overall experience with
the web in general)
2. Disable all add-ons that might also block ads on YouTube, **only keep
uBlock origin**
3. If you have any, disable all your custom filters for YouTube
4. Open the uBlock origin options and:
 1. Go in "Filter lists"
 2. Click on "Purge all caches"
 3. Click on "Update now"

As a bonus, remember that
[uBlock origin works best on Firefox](https://github.com/gorhill/uBlock/wiki/uBlock-Origin-works-best-on-Firefox).

I will not recommend any apps of the likes of (Re)Vanced as it still relies on
an official YouTube app which is completely closed-source (although the
patches are open).  
All it takes for Google to take down those patched versions, as shown in the
past, is a small cease-and-desist, while completely open-source projects have
absolutely no real grounds to be taken down (the RIAA tried, they failed).

As some closing words, remember that ads are a really predatory ecosystem that
prey on your attention only to track you to sell you stuff you probably don't
need.  
Having a content blocker is good for privacy but is also a good way of
de-cluttering the web and making it *somewhat bearable* to navigate (it also
improves security **a lot** for older users that might fall for scams and
viruses being spread through ads).  
So do you have a friend, coworker or family member that still has millions of
ads on their screen? Do them a favour and show them how to install uBlock
origin on their browser.

This website will **never** have ads, if it ever does, block it as it won't be
controlled by me then.

I'll see you next time!

---

If you liked this post, don't forget to subscribe to the blog via [RSS](/blog/index.xml) or [JSON](/blog/index.json).  
You can support me on [Ko-Fi](https://ko-fi.com/j4dlc).
