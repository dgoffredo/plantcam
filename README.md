Plant Time-lapse Camera
=======================
My mom gave me her old phone.  Now I use it to generate time-lapse videos of my
plants.

There are a few problems to solve:

- I have to remove the photos from the phone pretty regularly, or else the
  phone's storage will fill up.
- When the lights are off, the picture is almost entirely black.  I want to
  detect that and discard those images.
- The intervalometer app on the phone doesn't let me manually set the exposure
  or focus, so one image can vary from the next.  Not much I can do about that.
- The camera sometimes takes the picture upside down.  It's not just the EXIF
  orientation -- the pixels are actually rotated 180 degrees.  I want to
  detect that and rotate those images.  This is the tricky part.

I use `rsync` to move the images from the phone onto my server, imagemagick
(`magick`) to process the images, and `ffmpeg` to create the video.

It all happens in `./sync`, run as a `cron` job on the server every hour.

Once in a while I generate the time-lapse and post it to the bottom of
<https://lookatmyplants.com>.
