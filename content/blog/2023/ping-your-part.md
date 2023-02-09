---
title: "Ping your part!"
date: 2023-02-09
picurl: "https://bm.777.tf/web/blog/canvas/ping_your_part.avif"
picalt: "Propaganda poster with a roblox character and a text saying Defend the Canvas, Ping your Part"
picdesc: "Montage by AGPL_fanatic in the Furry Tech room"
draft: true
---

On February 6th 2023, Cameron Steel introduced the world to the IPv6 Canvas via [a blog post of his](https://blog.tugzrida.xyz/2023/02/06/introducing-the-ipv6-canvas/).  
The idea is simple: a 256x256 pixel grid where you have to ping an IPv6 to change a pixel.  
Basically, each pixel has its own address, referencing X and Y position but also RGB values, making it possible to print a variety of images all accross it.

Early in the launch, there was already this little guy:

![Dancing among us character doing the distraction dance.](https://bm.777.tf/web/blog/canvas/amogus.gif)

I originally discovered the project in the morning of February 7th, via the Ungleich IPv6 Matrix room.  
I immediately started tinkering with Python to try and print an image.

At first, I started generating the addresses.  
Doing so is really easy, just take the base address and fill out the gaps with values:

```python
base_address = "2400:8902:e001:233"
pixels = []

def make_image_and_start(ox, oy, image_path, to_file=False, filename="image.txt"):
    image = Image.open(image_path).convert("RGBA")
    max_w, max_h = image.size

    curr_w, curr_h = 0, 0

    start_w = int(ox)
    start_h = int(oy)

    max_w -= 1
    max_h -= 1

    # Now, let's convert the image
    while True:
        coordinates = x, y = curr_w, curr_h
        r, g, b, a = image.getpixel(coordinates)

        print(f"Converting: {x},{y} -> {r}:{g}:{b}/{a}", end="\r")

        # Check for alpha (transparency support)
        if a > 0:
            pixels.append(make_address(curr_w + start_w, curr_h + start_h, r, g, b))

        # Basic printer that goes left-> right and starts again
        if curr_h == max_h:
            curr_h = 0
            curr_w += 1
        else:
            curr_h += 1

        if curr_w == max_w and curr_h == max_h:
            curr_h = start_h
            curr_w = start_w
            break
```

Then, my original thought was to start using the `ping` command but it ended up being slow, taking half an hour to draw even half of the original image.  
That's when I had the idea of outputting everything in a text file and then using `fastping -f` on top of it which was working better!

Still, there was lots of room for improvement and it showed when the whole canvas was replaced with a moving rickroll (nicely done btw).  
Few hours later, a friend started testing `oping` which turns out to be faster than `fastping`.  
That method worked great until I finally started using raw sockets in my own script:

```python
sock = socket(socket.AF_INET6, socket.SOCK_RAW, socket.IPPROTO_ICMPV6)

def do_ping(dest_addr, timeout=1):
    print(f"Rendering current: {dest_addr}", end="\r")

    try:
        # Raw sockets, who cares, it's fast
        sock.sendto(b"\x80\0\0\0\0\0\0\0", (dest_addr, 0))
    except:
        # We don't care about failing
        # The pixel is usually re-written in next pass
        pass
```

At first, the program would crash, citing a buffer space error.  
Just ignoring the error makes it work and the loss is negligible since multiple passes are done quickly.

Victory, I could now draw images super fast which protected my artwork from attacks after.  
You can [see the source of the writer on SourceHut](https://git.sr.ht/~jae/PixelPinger).

![Pixelated canvas with: a Super Mario 64 logo, a big trans flag with Jae the Synth, an image of a husky in a LGBT hoodie and various texts and smaller images around.](https://bm.777.tf/web/blog/canvas/canvas.png)

All in all, this was a great experiment and I want to thank Cameron for creating it in the first place.  
I am currently trying to implement my own canvas which would be a tad bigger.

Also, thanks to everybody that participated in good faith, was lots of fun!

That's it for this post and I'll see you in the next one!

---

If you liked this post, consider adding it to your [RSS](/blog/index.xml) or [JSON](/blog/index.json) feed reader :)  
Canvas screenshot and amogus GIF provided by Cameron Steel.
