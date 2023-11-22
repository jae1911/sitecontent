---
title: "The problem of centralisation"
date: 2020-11-05T18:13:11+01:00
draft: false
description: "As you may have saw it, Github (Microsoft) recently banned youtube-dl from their platform after a DMCA request of the RIAA lobby..."
tags: ["copyright"]
---

Greetings,

As you may have saw it, Github (Microsoft) recently [banned youtube-dl](https://github.com/ytdl-org/youtube-dl/) from their platform after a DMCA request of the RIAA lobby.

This incident has exposed a bigger problem: **when do we decentralize code**?

For now, people are using the centralized Github (Gitlab.com counts as well) for **a lot** of projects, at the point where Github is the website with the most software repositories in the world with more than [48M users](https://github.com/search?q=type:user&type=Users) and [195M repositories](https://github.com/search).

With such success, it is only natural that new developers choose Github to start their journey, it is pretty fast, can be used for free and has **lots** of people on it; but there is a catch: as you accept it when you create your account, Github can terminate any repo, any account for any reason they want and whenever they want (even if you didn't broke the TOS) which gives them an unprecedented power on FOSS development.

The youtube-dl fiasco is only a reminder of how Github could harm the FLOSS community by completely wiping entiere projects with only the switch of a button (and sometimes, some annoying lobbies).

Then, what do we do?

We need to **decentralize Git** more. As speaking now, some solution already are somewhat decentralized, not requiring an account to contribute and working mainly with e-mails. We need more, a system where everyone could have its own little private island of code and then federate with others to happily share and contribute.

Some projects aim to solve that over-centralization problem:

- [ForgeFed](https://forgefed.peers.community/): an extension to the [ActivityPub](https://www.w3.org/TR/activitypub/) protocol to support Git
- [Git-send-email](https://www.git-scm.com/docs/git-send-email): a built-in function in Git to send changes via e-mail

Sadly for now, as you can see there is not a lot of alternatives but with some time, those can **only improve**!

So join the movment, delete your Github account and host your own repos, it will be healthier for FOSS!

That’s all for today,

I'll see you next time!

---

If you like my content, [don't forget to subscribe throught RSS](/blog/index.xml)!
