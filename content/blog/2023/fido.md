---
title: "Using FIDO keys"
description: "Security keys, FIDO, and more! How do I use those and why."
draft: true
date: 2023-12-08
---

Hey there everybody!  
Today, we're gonna talk about FIDO, and more generally about security keys.

${toc}

## FIDO and security keys?



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

The Yubikey is the first ever security I got.  
Nothing else much can be said except that it works well and is pretty much a plug-and-play solution.  
I only have two complains about Yubikey:

1. The firmware is completely locked, closed-source and impossible to update, which can make it pretty bad if the firmware the key was shipped with has security holes in it (as a matter of fact, [that already happened back in 2017](https://support.yubico.com/hc/en-us/articles/360021803580))
2. Given their early grip on the market, lots of websites and solutions will often only support Yubico OTP instead of the FIDO standard which makes it unable to use other brands of security keys (Hetzner is guilty of this for instance)

Otherwise, good hardware, works correctly.

### Solokeys V2

*Now, here comes the review I originally planned to release months ago.*  
Putting aside all the delays and the two years of waiting, I was excited to receive my Solokeys since they are completely Open-Source and the firmware can be upgraded, unlike with Yubikeys.

So, I received two Solokeys, one USB-A and one USB-C as well as the pledge goal reward being small colorful silicone protective covers for the keys.  
Right off the bat, looking at the USB-C one, the connect feels very fragile, like it would easily break if plugged too hard somewhere. The USB-A model looked fine and has no apparently hardware issues.  
Once plugging those for the first time, the experience was *not great*, being either not detected at all or just very jittery (NFC was completely nonworking).  
Luckily, a firmware update patched that and the keys started working as expected, though I must say that the NFC function doesn't works as well as the Yubikey on my phone (an iPhone).  
I am also having an odd issue where if the USB-A Solokeys isn't plugged facing the "right direction", it will not work and I will have to turn it around for it to work.  
It wouldn't be surprising with a normal USB-A plug, until you realize the Solokeys V2 have reversible USB.

Other than that, they work as expected everywhere that has support.

### My use

I basically use security keys everywhere I can, be it on external websites like Gandi or my internal stuff, either through native support like with FireFish or through a SSO solution like KeyCloak.  
I do also use my keys as passkeys when available as they are extremely convenient.

I'm extremely happy to see more and more websites and software supporting that kind of hardware, for instance, Discord recently added support for security keys as 2FA, Google and Microsoft allow passwordless passkey singups.

---

So this post was longer than usual.  
Reason is that writing posts takes way longer than I expected and finding good subject for those is equally hard.  
I'm trying to find more subject to write about in a more lengthy form factor, so stay tuned!

That's all for today.  
I'll see you next time!

---

If you liked this post, don't forget to subscribe to the blog via [RSS](/blog/index.xml) or [JSON](/blog/index.json).  
This website has no ads or tracking and will never have any, you can support me on [Ko-Fi](https://ko-fi.com/j4dlc) to maintain it alive.
