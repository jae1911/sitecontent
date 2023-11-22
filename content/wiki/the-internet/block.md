---
title: "Block. Those. Ads."
---

# Block. Those. Ads.

It is when I start using a brand new computer/install or somebody else's computer that I am reminded how unusable is the web without a good blocker.

Many popular websites have tons of ads (for instance `youtube.com`) that render the web painful.

For instance, it has been reported that `youtube.com` was reported to [sneakily test 5 ads before a video instead of "only" two](https://web.archive.org/web/20220916082524/https://www.developpez.com/actu/336584/YouTube-Free-teste-discretement-5-publicites-au-lieu-de-2-avant-le-debut-de-votre-video-la-fonctionnalite-est-en-cours-de-test/) (Archived link on `web.archive.org`).

The worst part is that [spendings allocated to advertising continue growing](https://www.statista.com/statistics/273288/advertising-spending-worldwide/) and given how it is headed, we won't see the end of it soon.  
It goes without saying that all those targetted ads need enormous amounts of data to be fed into them which adds to the annoyance, a true privacy nightmare.

Some websites will also render the web inaccessible by putting an undiscardable cookie popup that you have to pay to remove if you do not accept cookies, that is the case for the french website `jeuxvideos.com`:

[![Screenshot of the french website JeuxVideos.com blocking you access to the website if you don't access cookies and refuse to pay](https://bm.jae.fi/web/jae.fi/wiki/block/2022-09-25.09-32-08.png)](https://bm.jae.fi/web/jae.fi/wiki/block/2022-09-25.09-32-08.png)

There is also the fact that soon, [Chromium will be even less efficient at blocking ads](https://developer.chrome.com/docs/extensions/mv3/mv2-sunset/) while [Chromium was already greatly behind Firefox when it comes to blocking unwanted stuff](https://github.com/gorhill/uBlock/wiki/uBlock-Origin-works-best-on-Firefox).

---

Now what do we do? Are we all doomed already? The answer is no!  
Here are few steps you can take to at least mitigate all of this:

1.  Use [Mozilla Firefox](https://www.mozilla.org/en-US/firefox/new/) or a Firefox fork like [LibreWolf](https://librewolf.net/)
2.  Install [uBlock Origin](https://addons.mozilla.org/en-US/firefox/addon/ublock-origin/) which is a must-have add-on to block from tracking scripts to cookie pop-ups (at least certain pop-ups)

Let's extend a bit on the subject of uBlock, that add-on can do miracles. For a concrete example, let's take our undiscardable cookie popup from `jeuxvideos.com`:

[![Screenshot of the french website JeuxVideos.com blocking you access to the website if you don't access cookies and refuse to pay](https://bm.jae.fi/web/jae.fi/wiki/block/2022-09-25.09-32-08.png)](https://bm.jae.fi/web/jae.fi/wiki/block/2022-09-25.09-32-08.png)

In uBlock, there is a "pick" feature which means you can interactively select elements on a page to block. Let's do that for `jeuxvideos.com`:

<video controls alt="Video showing how to block the annoying cookie popup on JeuxVideos.com">
    <source src="https://bm.jae.fi/web/jae.fi/wiki/block/2022-09-25%2009-46-24.mp4" type="video/mp4">
    Your browser doesn't supports the video tag.
</video>

And voilà, you can now enjoy articles for free.  
uBlock also has many more features where you can block:

- Remote fonts
- Large media elements
- Pop-ups
- JavaScript

You can even make your own blocklists or just those others made.

Another way to bypass those annoying pop-ups (and sometimes even paywalls) is the reader mode of Firefox which can be accessed by clicking the small icon at the right of the URI bar (see on video near the end).

Before ending this, here are some blocklist recommendations for uBlock (you can find most of them in the "Filter lists" section of the configuration; you can also import lists from URIs at the very bottom of the page):

- Your regional language lists (under "Region, languages" category)
- [Anti-AdBlock killer](https://github.com/reek/anti-adblock-killer/)
- [1Hosts Pro](https://github.com/badmojr/1Hosts)
