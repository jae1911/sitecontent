---
title: "Matrix spam"
date: 2022-05-02
tags: ["tech"]
---

Greetings everybody.

If you are on the Matrix network, you probably noticed that some new spam waves are coming in these days.

Let's go through a small history of spam waves I experienced while moderating rooms there.

## The "classic" spam

This one was the first one I encountered and is the simplest form of spam. Basically, a user joins a room and then starts sending lots of messages usually containing the same text.

Those ones are easy to ban because it is the doing of only one user that is relatively easy to find.

## The "gore" spam

This one was also a early one I encountered and the principle is exactly the same as the classic spam except instead of message, the user will send gore images.

The thing is that in plus of the annoying nature of the spam, the disgusting imagery will likely make lots of people leave until the situation is resolved and the messages deleted.

It is resolved pretty easily like the classic spam.

## The "mass join" spam

This is the method that has been used recently to slow down servers.Basically a certain user will take advantage of outdated and open servers that don't check anything for registrations (no email, 3PID or captcha) to register thousands of accounts (event tens of thousands in some cases) and then make them join a single room at the same time.

The federation lag caused by the mass join will render most servers in the room inactive as they have to catch up with federation (no event priority yet).

Sometimes, the bot owners might also spam the room with messages in the meanwhile to add a bit more of hell into this.This is the spam method that has been used against [Furry Tech](https://furry.lol/) on March 1st 2022 in an attack that started at around 06:00 (Europe/Helsinki timezone).

> Thanks to Tulir for compiling [lists of user joins in spam waves](https://mau.dev/maunium/moderation/-/tree/main/spam).

While my server (jae.fi) got the federation pretty much figured out pretty quickly (within two hours of the attack), some other servers (like the-apothecary.club) is still struggling with the backlog at the moment I am writing these lines and hasn't federated any room changes yet (ACL, power level change, room access change).

To mitigate this spam attack type, I mainly put the room on invites only (invites are restricted to admins) and fired up Mjolnir to do the big of the work.I also compiled a ban list with (almost) all domains that started spamming.

In the meanwhile, another admin of the room started contacting homeserver managers (when it was possible) to let them know of this problem.Some of them acted very quickly and I want to thank them for that. Those servers got (of course) unbanned as soon as the mess was cleaned on their side.

Now the room has hundreds of servers in the ACL list but we are unlisting the servers where the managers are responding positively and are patching the problem.

So if you are a homeserver owner, please, please, if you want to run open registrations, add some sort of gatekeeper, an email confirmation, a 3PID or even a small captcha.

> Good remark from Dezponia in the Furry Tech channel:  
> "[...] homeserver admins that know they don' t need user registration, because the intent of the server is to be a single user instance for themselves, or just manual invites for friends, should disable registration entirely. Fast and easy to do and most likely the case for a lot of these servers since synapse had registration enabled by default until recently."

This avoids that a single bad actor just creates thousands of random accounts in one go via a single API endpoint.Note that it will never stop spam completely but will at least render it more painful to setup in the first place.

That's all for today and I'll see you next time!If you liked that blog post, don't forget to subscribe to it via RSS and if you have any questions, feedback or just want to say hello, join my Matrix room (all of that is in the blog header)

P.S: a [PR has been created](https://github.com/matrix-org/mjolnir/pull/291) to the moderation bot Mjolnir to be able to kick most bots in one go.
