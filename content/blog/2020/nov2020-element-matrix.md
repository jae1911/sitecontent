---
title: "Using Matrix to replace proprietary and centralized chat apps"
date: 2020-11-14T11:42:13+01:00
draft: false
description: "As you may know it, I am a fervent user of the chat protocol Matrix..."
hacker_news_id: "25091614"
featured: true
tags: ["software"]
---

As you may know it, I am a fervent user of the chat protocol Matrix.
If you don't know what Matrix is, this is basically a protocol developed by the Matrix Foundation. Matrix is made to be federated, it means that servers implementing correctly the Matrix specification can communicate and therefore, users that are not on the same servers can still talk to each other. Some examples of federation would be with Activitypub (Mastodon) or Usenet.

> But wait Jae, we already have countless other chat apps already, Telegram, Signal and even XMPP which is federated!

Well, here are the advantages of Matrix over all of those:

1. Matrix is 100% open-source. As you may know Telegram's servers are currently closed-source which poses a problem about trust. Nobody can say what the server is doing nor what it is harvesting which could be very dangerous. On the other hand, Signal, XMPP and Matrix are all fully open-source.

2. Matrix isn't centralized to a single server. Currently, Telegram and Signal are centralized apps which means if the server goes down, everyone else goes down. moxie0 of Signal even wrote a [blog post](https://signal.org/blog/the-ecosystem-is-moving/) on 'why Signal will never have federation' which is in my opinion a big mistake. XMPP still stands up as it is federated as well and has plenty of server implementations.

3. Matrix has a flagship client which has a great UX. **This** is a big point, as other federated protocols such as XMPP are kinda like a jungle for new users, you are greeted with a list of all clients which you can use and then comes the step where you have to choose your server. Lots of those servers are sometime hard to find, have very spartan UIs or even no web form or easy way to register whatsoever. On the other hand, Matrix has a flagship, **Element**, which is deemed as the 'official Matrix client' since it implements the Matrix specification correctly and is made by basically the same people. While other projects would have only done a server, Element made a polished client, focused mainly on the UX in order for people to take the first steps of moving to anything else easier. Even if the UX is still not perfect and some aspects aren't finished yet, moving to Element will be easier than moving to any other XMPP client.

I have been using Matrix since 2016 now and it has considerably improved over time, coming from "barely usable" to "let's host my own homeserver".
Even in its current state, lots of things are to be improved such as communities or custom stickers but everything is on the right way.
From now on, everything can **only improve**, we are seeing new server implementations, new clients, bots, communities moving to Matrix.

Matrix has several other features such as E2EE (end-to-end encryption) which is now enabled by default and bridges which can be used to temporarily bridge a Matrix room and a slack chat for instance.

If you want to give Matrix a try, download [Element](https://element.io) and create an account, it doesn't even requires an email address!
You can also come and say 'hello' in my very own channel **#home:jae.moe** !

That’s all for today,
I'll see you next time!
If you like my content, [don't forget to subscribe through RSS](/blog/index.xml)!
