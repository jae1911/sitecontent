---
title: 'Using an old laptop'
date: 2023-03-09
tags: ["tech", "hardware"]
draft: true
---

Hey there everybody!  
Few weeks ago, I received a ThinkPad x200 running Linux and with CoreBoot as a bonus.  
As other friends, I thought such a device (released in 2009) would be too old to do anything modern but I was greatly surprised.

This ThinkPad has some upgrades:

 - 8GB of RAM (unlike the official max of 4GB)
 - 1TB SSD
 - LibreBoot BIOS installed
 - Atheros AR9380 AR5BHB112 (400Mbps)

Which makes it a bit more comfortable to use.  
Of course, the machine is properly baptized with stickers (will update the stickers page with it when I receive my own ones).  

The two most dated aspects of the computer are its screen and CPU.  
While the screen has a low resolution for today's standard, it is still fairly usable and looks well enough (in some desktop environments, there is a yellow backlight for some reason that doesn't appears on i3).  
The CPU is what will mostly limit you when trying to compile something but as long as you don't run Gentoo, that shouldn't really be a problem (most of the compiled stuff I use from the AUR comes in `-bin` so no need to waste precious CPU cycles for that).

To have an extra-comfy setup, I took some time to configure stuff I always forget about on my main setup, for instance: MPD (Music Player Daemon).  
My config for it is very simple and works perfectly:
```conf
music_directory    "~/Music"

db_file            "~/.config/mpd/database"
playlist_directory "~/.config/mpd/playlists"

auto_update "yes"
bind_to_address "127.0.0.1"
restore_paused "yes"
max_output_buffer_size "16384"

audio_output {
    type "pipewire"
    name "pipewire"
}
```

In bonus, it can even play MOD, S3M, SID and XM formats which I wasn't aware, but was a welcome surprise.

Also, given the age of the laptop, using Kitty (which is the terminal emulator I usually use) is out of the question as the maximum OpenGL version supported by the laptop's GPU is 2.1 while the terminal emulator requires at least 3.3.
```
[068 11:30:32.926880] [glfw error 65543]: GLX: Failed to create context: GLXBadFBConfig
[068 11:30:32.926938] Failed to create GLFW temp window! This usually happens because of old/broken OpenGL drivers. kitty requires working OpenGL 3.3 drivers.
```

Instead, I use Alacritty on this machine which works good enough. The config itself is also pretty simple:
```yml
window:
  padding:
   x: 8
   y: 8
  opacity: 0.9

font:
  size: 9
  normal:
    family: Bok MonteCarlo

colors:

  primary:
    background: '#1b1b25'
    foreground: '#dedede'

  normal:
    black:   '#15121c'
    red:     '#cb5760'
    green:   '#999f63'
    yellow:  '#d4a067'
    blue:    '#6c90a8'
    magenta: '#776690'
    cyan:    '#528a9b'
    white:   '#eeffff'

  bright:
    black:   '#727480'
    red:     '#cb5760'
    green:   '#999f63'
    yellow:  '#d4a067'
    blue:    '#6c90a8'
    magenta: '#776690'
    cyan:    '#528a9b'
    white:   '#eeffff'
```

Also, one of the first things I did when I got the laptop was to update LibreBoot on it.  
I ended up [documenting the method on its own wiki page](/wiki/documentation/x200).

On the side of doing 'real work' on it, of course, given the age of the CPU (it being an Intel Core 2 P8600 which is two cores, two threads at 2.4Ghz), some stuff will be slower.  
For instance, when starting to work on Overengine, starting the development environment with `yarn dev` will take around 3s more than on my main workstation, so a bit slower but not that killing.  
The main difference is when compiling programs where it takes almost twice as much time. Luckily, on Arch, you can get most of the AUR in a pre-compiled format.  
When working on personal stuff, it takes a bit longer to test things, but having worked with low-end machines a good part of my life, it's still faster than some machines I had to use in the past.  
On the browser side, surprisingly, it runs pretty smoothly with Firefox+uBlock origin.  
Of course, websites with plenty of animations will have a bit harder time, but still surprisingly usable. It is to be noted that some websites like the Internet Archive Wayback Machine will not work on this laptop for some reason.  
I haven't really reached a tab limit as I rarely have more than 3 open at all times when working or doing anything ordinary.

In some months, I'll have to be away for some weeks, this will be the occasion to test this machine as a real daily driver instead of just a main portable (for now I'm still mainly using my fixed workstation at home and then the laptop in bed).  

That's all for today's post and I'll you peeps next time!

---

If you liked this post, don't forget to subscribe to the blog via [RSS](/blog/index.xml) or [JSON](/blog/index.json).  
If you wish to support the Open Services, a [LiberaPay page](https://liberapay.com/Jae) is available.
