---
title: "VR Dev Log"
description: "Devlog of my VR game"
menus: ["main"]
---

# VR Dev Log

I recently started making a VR game.  
You will find here most updates.

<iframe frameborder="0" src="https://itch.io/embed/2438380?bg_color=000000&amp;fg_color=ffffff&amp;link_color=c45bfa&amp;border_color=ac16ff" width="552" height="167"><a href="https://j4lc.itch.io/udwxr">Underworld XR I by Jae</a></iframe>

${toc}

## 2023-12-17

I spent most of this day playing with tools and setting up the base of the game.  
I the end, I have a flat world with a few objects including a grabbable one!

<iframe title="2023-12-17 21-02-14 - Basic Movement + Grab test" width="560" height="315" src="https://v.j4.lc/videos/embed/a02eed15-44db-443a-9ba4-36ff6bdf27e1" frameborder="0" allowfullscreen="" sandbox="allow-same-origin allow-scripts allow-popups"></iframe>

## 2023-12-18

Today, I spent some time experimenting with basic shaders.

<iframe title="2023-12-18 02-08-43 - Basic Shaders test" width="560" height="315" src="https://v.j4.lc/videos/embed/e36e60f2-221d-4e45-aeda-ddf06401d4cb" frameborder="0" allowfullscreen="" sandbox="allow-same-origin allow-scripts allow-popups"></iframe>

I also added a small debug screen on the back of the right hand:

![Yellow hand with a panel on its back displaying information.](https://i.j4.lc/ShareX/2023/12/Godot_v4.2.1-stable_mono_win64_t7B0O05Q5L.png)

## 2023-12-19

Today, I added a custom logging framework that basically will dump some data at the start of the game and allows for... logging.

![Log file showing some game data.](https://i.j4.lc/ShareX/2023/12/Code_XnY2T70mAu.png)

I also finished making basic touch tips to later make buttons and other interractables.

![Cube with written on it "I'm bad at making game" with a yellow hand with a blue lines everywhere showing colliders.](https://i.j4.lc/ShareX/2023/12/Godot_v4.2.1-stable_mono_win64_QDMgN03jZB.png)

## 2023-12-21

More improvements today, added support for Discord RPC.

![Discord screenshot showing the game status and logo.](https://i.j4.lc/ShareX/2023/12/Discord_NfjHxKQ1VX.png)

Also now exit buttons are functional and exit the game gracefully.

![White square with cyan text saying "EXIT"](https://i.j4.lc/ShareX/2023/12/Godot_v4.2.1-stable_mono_win64_vGY5VcjHYi.png)

Other improvements are to come, currently working on the initial game area.

## 2023-12-23

Not much today, just some stuff outside of the game itself:

- Setting up the [Itch page for the game](https://j4lc.itch.io/udwxr)

## 2023-12-24

Today, big addition, the first game area was added as well as some fog.  
It's far from finished but a big step nonetheless.

<iframe title="2023-12-24 12-53-11" width="560" height="315" src="https://v.j4.lc/videos/embed/0bdd9af9-60f4-4b5c-856f-73d216c112de" frameborder="0" allowfullscreen="" sandbox="allow-same-origin allow-scripts allow-popups"></iframe>

## 2023-12-25

Today, small beta release, the 0.4.  
Here is the changelog:

Added:

- Base of hand menu
- Holographic shader
- Popup generation utility
- DebugInfo library  
  -- Shows game and computer performance RT if game is launched in debug mode
- Complete logging framework  
  -- Completely custom for now  
  -- Dumps the computers stats on start  
  -- Support log levelling
- Basic metal shader
- Touch buttons
- Basic test spawnbox
- Working graceful exit button
- Discord RPC  
  -- Discord RPC is done via an external library for now  
  -- In the future, it will be switched to the official Discord game SDK
- Basic home scene
- Automatic publishing to Itch.io

Patched:

- Grip strenght for grab  
  -- It is now easier to grab objects
- Pin SDK version to avoid build issues
- Bump Godot version to avoid build issues
- Use built-in methods instead of relying on external package for stats
- Make sure the C# language version is set on latest

Changed:

- Replaced placeholders to the studio assets
