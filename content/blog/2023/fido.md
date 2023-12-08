---
title: "Using FIDO keys"
description: "Security keys, FIDO, and more! How do I use those and why."
draft: false
date: 2023-12-08
---

Hey there everybody!  
Today, we're gonna talk about FIDO, and more generally about security keys.

${toc}

## FIDO and security keys?

### What's FIDO

FIDO (standing for Fast IDentity Online) is a set of open standards created by the very originally named FIDO Alliance, designed to address the limitations of traditional password-based authentication.  
This set of open standards include:

- U2F (Universal 2nd Factor) - Is made to strengthen and simplify 2FA using USB or NFC hardware; nowadays it is succeeded by FIDO2 and CTAP2
- CTAP2 (Client to Authenticator Protocol) - Enables interoperability between an authenticator (phone, security key) and a client (a computer)
- FIDO2 - The one on everybody's lips, consists of WebAuthn (published by W3C) and CTAP2 and specifies a standard authentication protocol

### Why use it

The main thing that sold security keys to me is the hardware component brought into authentication.  
It may not be as practical as just pulling an OTP code from a password manager but adds a pretty strong layer of security to logins as you need to have the physical hardware and touch it to allow a login to go through.  
Same for passwordless logins, I find them more convenient than using a password and automatically thwarts any phishing attempts (which is extremely good for end users that might not be that tech-savvy).

Regular OTP is also prone to attacks, be it [the incompetence of OTP app providers providing a sync](https://nitter.net/mysk_co/status/1651021165727477763), your password manager getting compromised or just SIM swap attacks (being a bit more exotic though increasing, according to [a TWSJ citing FBI numbers](https://archive.is/og8go)).

### Caveats

The main caveat of hardware keys is, of course, if your key ever gets stolen or lost.  
That's why it's important to have backups (usually a second key).  
While stealing a security key is harder than phishing a password, it still can be a possibility if you are being personally targetted by _really persistent_ malicious actors (don't become too paranoid about this though, this doesn't concerns 99.9% of users, the "lost key" scenario is way more probable for you than anything else).  
In case of a stolen or lost key, FIDO2 mandates that the user needs to authenticate before being used, be it phone/computer authentication, biometrics or a PIN (most common for security keys).

Technically, this still doesn't accounts for attacks like bruteforcing, where someone could just try and test all PIN combination possible.  
Some keys like the Yubikey have a protection against this, after three failed attempts, the attacker will have to unplug and plug again the device, and after seven (in a row mind you), the key will wipe its FIDO2 store.

That kind of protection also means someone can easily sabotage your keys and render them unusable.  
Best protections would be:

- Keep the main security key on you at all times
- Occasionally test your backup key(s)
- Make sure services have ways of recovering accounts and that those are up-to-date

Another caveat of physical security keys is the number of passkeys a single device can support.  
FIDO2 stores an unique FIDO2 key on the device itself for each service, this means different keys have different amounts of slots available to store those.  
For instance, the Yubikey 5 can store 25 passkeys, the Solokeys V2 50 while the new Google Titan Keys can store up to 250.  
This is an issue to be aware of for in the future, when passkeys will be more common.

### Where can you use it

In recent years, tons of websites added support for security keys.  
Biggest ones being Google, Microsoft and Apple, the two first ones allowing passwordless logins through passkeys.

Others can be cited like:

- GitHub
- Gandi
- ProtonMail
- DNSimple
- Bitwarden

The list could be way longer, those are just a tiny fraction of those who support it.  
You can see a good list of supported websites and apps on [passkeys.directory](https://passkeys.directory).

## Personal journey & use

Let's see my personal uses of security keys and which ones I have.

### A long, long wait

Back in July 2021, I backed the the Solokeys V2 IndieGoGo campaign, that were originally supposed to be released in June 2021.  
Sadly, Solokeys had delays due to supply chain and construction issues, pushing the release and shipment of the pledged keys to September of that same year. It's around that same time that surveys, asking what USB type you wanted for the keys and setting your delivery address were sent, giving the hope for a rapid delivery.

Fast forward to September, more delays, pushing delivery even further to October; but after waiting all of that time, what is one month more? (little did I know)  
All the way through end of 2021 and 2022, more and more delays were announced, always pushing further and further the delivery date.  
It's around that time I decided to purchase another brand of security key while waiting, a Yubikey 5 NFC (yes, a single one, I know having no backups is bad).

Finally, in August 2023, after two years of waiting, I received my two Solokeys V2, one USB-A and one USB-C.

### Yubikey

The Yubikey is the first ever security key I got.  
Nothing else much can be said except that it works well and is pretty much a plug-and-play solution.  
I only have two complains about Yubikey:

1. The firmware is completely locked, closed-source and impossible to update, which can make it pretty bad if the firmware the key was shipped with has security holes in it (as a matter of fact, [that already happened back in 2017](https://support.yubico.com/hc/en-us/articles/360021803580))
2. Given their early grip on the market, lots of websites and solutions will often only support Yubico OTP instead of the FIDO2 standard which makes it unable to use other brands of security keys ([Hetzner is guilty of this for instance](https://docs.hetzner.com/accounts-panel/accounts/two-factor-authentication/))

Otherwise, good hardware, works correctly.

### Solokeys V2

_Now, here comes the review I originally planned to release months ago._  
Putting aside all the delays and the two years of waiting, I was excited to receive my Solokeys since they are completely Open-Source and the firmware can be upgraded, unlike with Yubikeys.

So, I received two Solokeys, one USB-A and one USB-C as well as the pledge goal reward being small colourful silicone protective covers for the keys.  
Right off the bat, looking at the USB-C one, the connector feels very fragile, like it would easily break if plugged too hard somewhere. The USB-A model looked fine and has no apparently hardware issues.  
Once plugging those for the first time, the experience was _not great_, being either not detected at all or just very jittery (NFC was completely nonworking).  
Luckily, a firmware update patched that and the keys started working as expected, though I must say that the NFC function doesn't works as well as the Yubikey on my phone (an iPhone).  
I am also having an odd issue where if the USB-A Solokeys isn't plugged facing the "right direction", it will not work and I will have to turn it around for it to work.  
It wouldn't be surprising with a normal USB-A plug, until you realize the Solokeys V2 has reversible USB.

Another thing to have in mind is that if the first generation of Solokeys was FIDO certified, the V2 isn't _yet_.

Other than that, they work as expected everywhere that has support.

Given the current state of the project (as of 2023/12/08, no blog posts or communication since June 2023 and no commits in Solokeys V2 repos since January 2023), I sadly cannot recommend that solution and instead redirect people to Yubikey, that has been pretty solid for years.  
I also sent an email to the official contact point of Solokeys on December 2 2023 asking about the state of the project and still haven't got any response yet.  
This post will be updated when I receive an answer.

### My use

I basically use security keys everywhere I can, be it on external websites like Gandi or my internal stuff, either through native support like with FireFish or through a SSO solution like KeyCloak.  
I do also use my keys as passkeys when available as they are extremely convenient.

Small update: I'm also using my key for SSH now.

As a side note, when trying to register my Solokeys as a GitHub passkey, I was getting generic errors "Something went wrong" without any much more.  
Turns out that if your key is already registered for MFA, you will need to remove it before re-adding it as a passkey.

## Final words

I'm extremely happy to see more and more websites and software supporting that kind of hardware, for instance, Discord recently added support for security keys as 2FA, Google and Microsoft allow passwordless passkey sign-ups, and some other platforms that I use daily like Resonite plan to implement FIDO2 support in the future.

I can recommend anyone getting security keys and adding them everywhere you can.  
If you don't want to get hardware and trust your phone provider enough, both Android (through Google) and [iOS/macOS](https://support.apple.com/en-gb/guide/iphone/iphf538ea8d0/ios) support passkeys.  
I can also recommend the password manager [Bitwarden](https://bitwarden.com) which can store passkeys, allows login 2FA with FIDO2, is Open-Source and can be self-hosted.

Hopefully in the future, we can have even more FIDO2 support, not only as a 2FA but also as a passwordless way to login.

Also massive thanks to Dezponia, in the Furry Tech Matrix room, for the extensive feedback and additional information about how FIDO2 works and security practices they provided for this blog post.

---

So this post was longer than usual.  
Reason is that writing posts takes way longer than I expected and finding good subjects for those is equally hard, so instead of prioritizing quantity, I'm going for quality and length.  
I'm trying to find more subjects to write about in a more lengthy form factor, so stay tuned!

You also probably noticed that the font of this website changed completely and this has been done for a good reason: the old pixel font was extremely hard to read for longer texts, not very practical when you host a blog and a wiki with lore and other stuff people might want to read.  
Give a warm welcome to [Atkinson Hyperlegible by the Braille Institute](https://brailleinstitute.org/freefont), that will probably stay around for some time (unless I find a pixel font as easy to read as this one).  
Why this exact font? The software FireFish (that I use to post on ActivityPub) has an option for it and I liked it.

That's all for today.  
I'll see you next time!

---

If you liked this post, don't forget to subscribe to the blog via [RSS](/blog/index.xml) or [JSON](/blog/index.json).  
This website has no ads or tracking and will never have any, you can support me on [Ko-Fi](https://ko-fi.com/j4dlc) to maintain it alive.
