---
title: "The messengers I use every day"
date: 2021-01-18T09:35:58+01:00
draft: false
description: "Greetings, for the first blog post of the year, I'm gonna talk about what instant messengers I use, following the whatsapp fiasco."
tags: ["tech", "privacy"]
---

Greetings, for the first blog post of the year, I'm gonna talk about what instant messengers I use, following the whatsapp fiasco.
But first, I want to wish you a very happy new year, I hope this year will go smoothly this time.
Now that's it's done, let's dive right in shall we?

## Element (Matrix)

I talked about this one extensively in [this blog post]({{< ref "/blog/2020/nov2020-element-matrix.md" >}} "Using Matrix to replace proprietary and centralized chat apps") but tl;dr:
 - 100% Open-Source
 - Federated
 - Somewhat good UX
 - E2EE by default

If you want to try Element, you can go [on their official website](https://element.io) but please, pick another server than Matrix.org as it is already overloaded by too much users.
A good server list [can be found here](https://publiclist.anchel.nl).

## Signal

This one is a messenger I have been using for quite some time in a more professional setting as it is really easy and quick to setup.
All you need is a phone number and here you go!

The needed phone number is a big point of criticism as it could be used to identify you, **however** the Signal team said in a [Reddit AMA](https://teddit.net/r/technology/comments/kt91qk/signal_private_messenger_team_here_we_support_an/gikqpde/#c) that they are currently working on a way to use the app without a phone number (which is a good thing).

One of the best "selling points" (even tho it is not sold) of Signal is that **everything** is end-to-end encrypted.
It is also [advertised by Edward Snowden](https://nitter.net/Snowden/status/1347217810368442368) since quite some time now (since 2016 when it was called Open Whisper Systems).

Everything is Signal is [Open-Source](https://github.com/signalapp) (from the server to the clients) but self-hosting it isn't really useful as an individual it is **not federated**.

Sadly, Signal relies on nonfree Google Play Services but can be used without. There is also a [fork named Langis](https://langis.cloudfrancois.fr) which removes all Google Play Services dependencies.

## Threema

Threema is a Swiss messenger which has been around since 2012 and claims to have more than 8 million users ([January 2020](https://threema.ch/en/about)).

As like the other two, Threema is completely end-to-end encrypted but is the only one in the list which is paid (3CHF which is frankly nothing).

As the [apps are Open-Source](https://github.com/threema-ch), the backend of Threema is sadly not yet open.

The app itself doesn't contains any trackers and can be downloaded and used without the use of Google Services (even tho Firebase Cloud Messaging will be used *when available* in order to push notifications onto devices), they even have [their own shop](https://shop.threema.ch) on which you can buy a license and download the app.

Threema doesn't requires you to have a phone number or anything else to use the app and in fact, it can be used completely anonymously.

The overall quality of the app is extremely good and to its advantage, it got [a security audit](https://threema.ch/press-files/2_documentation/security_audit_report_threema_2020.pdf) in November 2020 which resulted in:

> Cure53 needs to underline that the overall impression of the code quality and general structure of the project can only be described as unusually solid. The design and implementation were clearly accomplished by a rare team of experienced and security affine engineers. In Cure53’s opinion, there should be no doubt about the focus of these processes being on providing a highly secure messaging application without encumbering the overall user-experience.

Which is actually a really good point in favor of Threema.

## To finish

In the end, I am using three messengers which I find refined and frankly good.

If you are a Whatsapp user and still haven't switched to something better, I urge you to do so, friends and family might even have already switched to something else like Signal.

On my part, I'll see you in the next blog post, if you liked this one, you can [subscribe through RSS](/en/blog/index.xml) so you dont' miss any future posts.
