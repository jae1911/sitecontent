---
title: "Converting images to videos"
---

# Converting images to videos

When trying to digitalize super 8 film, the scanner will output files following the format `PICT{number}.JPG`.

First, convert into a video:

```
ffmpeg -r 16 -f image2 -s 1920x1080 -i PIC%04d.JPG -vcodec libx264 -crf 25 -pix_fmt yuv420p raw.mp4
```

Now, to stabilize the video:

```
ffmpeg -i raw.mp4 -vf vidstabdetect=shakiness=7 -f null -
ffmpeg -i raw.mp4 -cf vidstabtransform=smoothing=30:zoom=5:input="transforms.trf" final.mp4
```

And done, the video should be perfect!
