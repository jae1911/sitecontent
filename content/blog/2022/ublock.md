---
title: "Let's make the web bearable"
date: 2022-12-30
draft: false
tags: ["tech", "software"]
---

For this last post of the year, let's see something simple: my personal uBlock Origin filters.  
If you don't know already, [uBlock Origin](https://github.com/gorhill/uBlock) is a powerful blocker for ads, trackers and many other things within your web browser.  
I personally use it on all my machines with Mozilla Firefox.

## YouTube blocks

By default, uBlock will do a great job at getting rid of most of the ads (if not all) and trackers present on the website but for me, it's not enough.  
I find lots of elements distracting on YouTube, including for instance, the comment section and related feeds. To block them, it's easy:

```
www.youtube.com###comments
www.youtube.com###related
```

And done, all is now removed.  
Problem is, when trying to block specific buttons, like the "share" or "clip" ones, those don't have any proper IDs which renders blocking a bit more tricky.  
We can work around this by matching the property `title` or `aria-label` instead:

```
www.youtube.com##[aria-label$="Create" i]
www.youtube.com##[title$="Shorts" i]
www.youtube.com##[title$="Trending" i]
www.youtube.com##[title$="Music" i]
www.youtube.com##[title$="Movies" i]
www.youtube.com##[title$="Gaming" i]
www.youtube.com##[title$="Sports" i]
www.youtube.com##[aria-label$="Clip" i]
www.youtube.com##[aria-label$="Share" i]
```

And done, everything useless is now removed.  
My full list of rules for YouTube goes as it follows:

```
## YOUTUBE FILTERS ##
www.youtube.com###comments
www.youtube.com##.ytp-ce-element
www.youtube.com###hover-overlays
www.youtube.com##yt-icon.ytd-badge-supported-renderer
www.youtube.com###related
www.youtube.com###donation-shelf
www.youtube.com###voice-search-button
www.youtube.com##.ytp-show-tiles.videowall-endscreen.ytp-player-content.html5-endscreen
www.youtube.com###guide-section-title

# Useless buttons
www.youtube.com##[aria-label$="Create" i]
www.youtube.com##[title$="Shorts" i]
www.youtube.com##[title$="Trending" i]
www.youtube.com##[title$="Music" i]
www.youtube.com##[title$="Movies" i]
www.youtube.com##[title$="Gaming" i]
www.youtube.com##[title$="Sports" i]
www.youtube.com##[aria-label$="Clip" i]
www.youtube.com##[aria-label$="Share" i]
```

Which will remove most of distracting trash lying around on the website.  
The main page could use some more rules but I'm working on that.

## Misc websites

Those are rules for misc websites from web shops to food delivery websites, everything else than monoliths like YouTube is there:

```
## MISC WEBSITES ##
partco.fi###cookieNotice
verkkokauppa.com##.special-days-ribbon-accordion
github.com###feed-next
github.com##.js-notice
github.com##[aria-label$="Explore Repositories" i]
dnsimple.com###dnsimple-support-wrapper
wolt.com##[data-test-id$="OrderBubble" i]
wolt.com##[data-test-id$="Discovery.AllLink" i]
wolt.com###footer
posti.fi###beta-posti-footer
```

## Website Blocks

However, there is some websites you can't improve, even with blocking annoying elements, this is where the full block comes in place.  
Some of the domains on my personal list are:

```
## DOMAINS BLOCKED ##
||reddit.com # Redirected via privacy addon
||twitter.com # Redirected via privacy addon
||facebook.com # Useless domain
||instagram.com # Useless domain
||pinterest.com # Useless domain
```

## Words of the end

Really simple and short post for today.  
Just to serve as a reminder: **BLOCK. THOSE. ADS.** and if you want to support your favorite creators, donate to them directly through whatever platforms they have.

Oh, also, happy new year in advance, let's hope 2023 will be brighter.
I'll see you next time!
