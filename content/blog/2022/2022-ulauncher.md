---
title: "uLauncher, my new friend"
date: 2022-01-01
---

Greetings peeps, first, happy new year, I hope 2022 will be a good year for you!

Now, let's go on with today's subject: [uLauncher](https://ulauncher.io/) which is in my mind the best application launcher around.

For the little backstory, I was trying to find OBS Studio in the horrendous default XFCE start menu (yes and as much as I love XFCE, I cannot use that damned menu). I then remembered that on macOS, we have that Spotlight search bar (that you trigger using CMD+SPACE) that has to be one of the most useful things.

I then started to search a bit around the web, only to find what I looked for: uLauncher.

> Note: thanks to [Cadence](https://cadence.moe) for mentioning the existence of [Krunner](https://userbase.kde.org/Plasma/Krunner) and [Kupfer](https://kupferlauncher.github.io/) that can fill out the exact same purpose.

Installing is effortless (at least on Arch) if you have an AUR package manager like Paru and is simply `paru -S ulauncher` (or `ulauncher-git` if you prefer to live on the edge).

After installation, a last `systemctl --user enable --now ulauncher.service` and you're all set, you can now try CTRL+SPACE to reveal the launcher and start typing.

But wait, there's more!

You can actually extend uLauncher with countless extensions which can do anything from calculating currencies to copying emojis. It is very random, but some of those are really useful.

My current setup uses those extensions:

 - Weather – Shows weather using the OpenWeatherMap API
 - PyPi – Allows you to search PyPi for packages
 - Calculate Anything – One of the most powerful extension that allows you to literally calculate anything from currency conversions to surface or pressure (will require you to run `pip3 install pytz pint simpleeval --user` before installing)
 - NPMJs – Same thing that PyPi but with NPM
 - Folder Search – Title
 - Emoji – Allows you to search and copy emojis
 - Symbol Search – Allows you to search and copy ASCII and Unicode symbols

In the configuration window, you will also find the search engine tab, which you can customize by bringing your own to it.

Well, I think that's enough for today, if you liked this article, you can [subscribe to this blog via RSS](/blog/index.xml).

Again, let me reiterate all my wishes of good health and happiness for this new year that is 2022.

I'll see you next time!
