---
title: "Announcing Overengine"
date: 2022-10-21T12:00:00+03:00
draft: false
---

Hey there!  
If you are present in my Matrix channel and generally in Matrix places where I also am, you may have seen I'm currently making my own blog engine which powers *this* very blog.

## Why my own blog engine

In the beginning, my website was a simple HTML single page, just saying where my GitHub and blog were.  
Then, I started making a small Wiki about random stuff which was using DokuWiki.

Later that year, I remade the main website using NextJS to try to learn it, it was pretty painful and not really efficient so I then, even later, replaced it by a static version.

With this website, I had the frequent complain that the CRT effect on screen was painful to look at, so time to make a new style.  
It's during that time that I came out with the CSS that is currently hosted on the website which is made to mimic oldskool websites.

As blog engine before, I was using Ghost.  
I originally chose Ghost because it is fairly easy to use and I didn't see all the influencer bullshit around it.  
At some point, an upgrade asked for a migration that never worked so I decided to go hunt for an alternative.

It's at that point I ended up using GoHugo *again* which is pretty solid only for one detail.  
In GoHugo, you have to specify that `baseURL` which is set in stone and not dynamic.  
For instance, if somebody tries to access the blog using TOR (which I have) or a mirror domain (which I also have), they will be stuck with lots of links and feeds generated with the main domain set in `baseURL`.

It's from that need that emerged this little project.

## Meet Overengine

Meet Overengine, my over-engineered, homebrew, blog engine.  
It is made in TypeScript (don't hate me, I have to learn this tech at the moment) and has several features:

 - Templating using EJS
 - Menus are configurable using Markdown YAML header
 - Blog Permalinks
 - ShortCodes (kind of)
 - Dynamic vhosts
 - Tagging (very basic)
 - External content folder without a need of rebuilding the app each time
 - ATOM, RSS and JSON feeds
 - Blog side warns if an article is old
 - BGP Widget
 - WakaTime widget
 - OpenWeatherMap widget

That's a lot of stuff so let me explain the ones people asked the most questions about.

### Dynamic vhosts

Basically, it's solving the problem encountered at the end of the part one of this post: GoHugo is set with that `baseURL` parameter.  
Using Overengine, everything is generated on the fly which means you can access the website from any domain and even through TOR without being affected in any way.

The best example is on the JSON feed. For instance, the JSON feed if accessed from `jae.fi`:

```json
{
    "version": "https://jsonfeed.org/version/1",
    "title": "Jae's Blog",
    "home_page_url": "https://jae.fi",
    "feed_url": "https://jae.fi/blog/index.json",
    "description": "The blog of Jae.",
}
```

And when accessed throught TOR:

```json
{
    "version": "https://jsonfeed.org/version/1",
    "title": "Jae's Blog",
    "home_page_url": "http://jaednob5azseoa2coeehrh2idwwqesu5mwvuqs3fwp3ekxhkl2lfpuyd.onion",
    "feed_url": "http://jaednob5azseoa2coeehrh2idwwqesu5mwvuqs3fwp3ekxhkl2lfpuyd.onion/blog/index.json",
    "description": "The blog of Jae.",
}
```

Which makes it possible to have a TOR-only setup for feeds for instance.


### Again, why make your own?

It's fun.

---

Of course, the software is Open-Source and under the MIT license, you can [check out the repo here](https://sr.ht/~jae/Overengine/).  
Also, check out the new feeds added by the software and don't forget to subscribe to those with your favourite reader/software/bot to not miss anything of the blog:

 - [JSON](/blog/index.json) `/blog/index.json`
 - [RSS](/blog/index.xml) `/blog/index.xml`
 - [ATOM](/blog/index.atom) `/blog/index.atom`

I'll see you next time!
