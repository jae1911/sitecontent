---
title: "One week of NixOS"
date: 2020-11-08T10:22:46+01:00
draft: false
description: "As you may have saw I on Mastodon, I am testing NixOS..."
hacker_news_id: "25024639"
---

As you may have seen I on Mastodon, I am testing NixOS for over a week now and here is a few comments about how the distro works and what doesn't work for me.

First, everything is NixOS is declared in a configuration file located at `/etc/nixos/configuration.nix` where you declare packages you want to install, services to start, udev rules, ECT, you get it.

This is the first very weird thing as you don't really install packages with the CLI directly (even if you can), instead you modify the config file and rebuild the system with `nixos-rebuild switch`.

NixOS is made in such a way that everything aims to be reproducible. An example: if you want to get the exact same setup as I have, you can just take [my configs repo](https://forge.tedomum.net/jae/nixos-configs), clone it on your NixOS installation, run `nixos-rebuild switch` and voilà, you will have the exact same programs as me installed in the same way with the same version (roughly).

In this distro, adding a user is really easy and goes like this:

```
{ config, pkgs, ... }:

{

    users.groups.plugdev = {};

    users.users.jae = {
        isNormalUser = true;
        extraGroups = [ "wheel" "docker" "adbusers" "plugdev" ];
        shell = pkgs.zsh;
        packages = with pkgs; [
            # Games
            minetest stepmania lutris-free pcsx2
            # Misc audio / video / image
            pulseeffects ffmpeg-full obs-studio inkscape krita
            # Useful software
            mumble qbittorrent libreoffice ledger-live-desktop
            # Dev
            jetbrains.idea-community lazygit gnome3.zenity insomnia jetbrains.rider mono msbuild dotnet-sdk_3 ganttproject-bin kubectx
            # SDR
            rtl-sdr gqrx gpredict noaa-apt welle-io
        ];
    };
    users.extraGroups.vboxusers.members = [ "jae" ];
}
```

Let's see what everything does!

```
 users.groups.plugdev = {};
```
Creates a group named `plugdev`, don't pay attention to it, it is just a test for the Ledger Live application.

```
 isNormalUser = true;
```
Tells the os that the current user is a normal one. It will create a home folder and set the default shell.

```
 extraGroups = [ "wheel" "docker" "adbusers" "plugdev" ];
```
Here, we are setting the groups the user is in to grant special permissions.

```
 shell = pkgs.zsh;
```
As you may have guessed it, we are setting the default user shell to ZSH.

```
 packages = with pkgs; [
            # Games
            minetest stepmania lutris-free pcsx2
            # Misc audio / video / image
            pulseeffects ffmpeg-full obs-studio inkscape krita
            # Useful software
            mumble qbittorrent libreoffice ledger-live-desktop
            # Dev
            jetbrains.idea-community lazygit gnome3.zenity insomnia jetbrains.rider mono msbuild dotnet-sdk_3 ganttproject-bin kubectx
            # SDR
            rtl-sdr gqrx gpredict noaa-apt welle-io
        ];
```
There, we are installing per-user packages because yes, NixOS supports that, any user can have its own packages that others users can't access.

> Correction from *hvdijk* on Hacker News, "*Other users can access those packages if they want to. Those packages won't show up in other users' $PATH, so other users will not be affected by them, but they could see what's in /nix/store if they wanted to. This matters when you're thinking of putting private data (such as an encryption key) in a package: it's vital that you don't do that on a multi-user system.*"

Configuring NixOS for a daily use is at the end very easy (although I am getting some trouble to get Ledger Live working; which is the biggest problem I've had so far).

Now, let's talk about where I got some trouble.
As you may know it, I am a dev and every day I need to compile, test, run and so on.
NixOS gave me some trouble to only run some programs from source such as [Element Desktop](https://element.io) or [TeDomum IMG](https://img.tedomum.net) as the way the system is built, lots of directories are read-only and programs can't be installed globally through NPM or PIP.
I ended up using Docker to build the apps (even if it took a bit more time).

Needless to say, almost every other project worked.
If you want NodeJS to start a project for instance, you can just do `nix-shell -p nodejs` and here you go, a shell with nodejs installed, ready to do what you want.

At the end, NixOS brings very interesting concepts such as a really great reproducibility but new users can feel lost as its way to work is really different from conventional Linux distributions.
I'll give NixOS more time and write a follow-up in some time to see how everything went.

If you want to give it a shot, the [official NixOS website awaits you](https://nixos.org/)!

That’s all for today,
I'll see you next time!
If you like my content, [don't forget to subscribe through RSS](/blog/index.xml)!
