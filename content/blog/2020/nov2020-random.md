---
title: "Redirector, Keyboard and foxes"
date: 2020-11-21T17:23:25+01:00
draft: false
description: "This week, nothing fancy, not a big article about a Federated media, not a tutorial on how to do things, just a small article to chill."
hacker_news_id: "25170880"
---

This week, nothing fancy, not a big article about a Federated media, not a tutorial on how to do things, just a small article to chill.

## Redirector

Few days ago, I discovered the Firefox addon Redirector ([which you can download here](https://addons.mozilla.org/fr/firefox/addon/redirector/)) which I now use as a subtitute for [Privacy Redirect](https://addons.mozilla.org/en-US/firefox/addon/privacy-redirect/) as Redirector is much more powerful.
As Privacy Redirect only supports Nitter, Invidous, Bibliogram and OpenStreetMap, the possibilities in Redirector are pretty much endless.

This addon features two modes to redirect stuff:
 - Wildcard, when you specify an url like this `https://example.com/*`
 - Regex, when you want to redirect an url like this `https://(www.)?example.(com)?/(*.)`

Here is some of my current settings:

 1. Redirect Twitter to Nitter

```
Redirect: https://(mobile.)?twitter.com/(.*)
to: https://nitter.tedomum.net/$2

Example: https://twitter.com/WholesomeMeme/status/1329846975575904256
→ https://nitter.tedomum.net/WholesomeMeme/status/1329846975575904256 
```

 2. Redirect Sciencedirect to Sci-Hub

```
Redirect: https://www.sciencedirect.com/science/article/pii/*
to: https://sci-hub.se/https://www.sciencedirect.com/science/article/pii/$1

Example: https://www.sciencedirect.com/science/article/pii/S1057521920302131
→ https://sci-hub.se/https://www.sciencedirect.com/science/article/pii/S1057521920302131 
```

 3. Mortify Amazon pages (to avoid tracking)
 
```
Redirect: https://(www.)?amazon.(.*).(.*)
to: https://darmarit.org/morty/?mortyurl=https://amazon.$2

Example: https://www.amazon.com/gp/product/B01EHMXCL0?linkId=a22cc4b646e241776ad8f630d3e9f2a3
→ https://darmarit.org/morty/?mortyurl=https://amazon.com/gp/product/B01EHMXCL0?linkId=a22cc4b646e241776ad8f630d3e9f2a
```

Don't hesitate to thinker by yourself to improve the efficiency of those redirects.

## XD75re keyboard

As you may have seen, I am now using a XD75re keyboard (since september) which runs on the Open-Source firmware [QMK](https://qmk.fm).
I chose the XD75re as it is a ortholinear keyboard, which, I wanted to test for quite some time now.
I primarily intended to buy a Typematrix but those turned out to be pretty much not modular enough with a price tag of around 110USD.

This is why I settled on the XD75re. Because it uses QMK (Quantum Mechanical Keyboard), everything can be modified, from the layout to the LED effects of the board, without any specific software (even tho the `qmk` cli utility is recommended to flash new layouts).

My very own keyboard uses:
 - Purple Outemu Switches
 - XD75re PCB
 - White low profile keycaps

With a price tag of around 95EUR for everything, it is somewhat affordable for a custom keyboard and even tho it takes some time to be used to the layout, really comfortable.

## Foxes

Do you guys love foxes? If so, you're in luck, I've discovered a small API that gives you a [random fox](https://randomfox.ca) for infinite cuteness!
Here is an example of this API, right into this page (refresh to see the fox change):

That’s all for today,
I'll see you next time!
If you like my content, [don't forget to subscribe through RSS](/blog/index.xml)!
