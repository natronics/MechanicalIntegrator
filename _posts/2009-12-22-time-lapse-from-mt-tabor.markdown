---
layout: post
title: Time Lapse from Mt Tabor
categories : [Pacific NW]
tags: [blender, pdx, Portland, time lapse, video]
---

--------------------------------------------------------------------------------
I like my camera as much as the next guy, but it's missing a feature: an
intervalometer. An intervalometer is a device or program that lets you take a
series of pictures in a row at some interval. This lets you do, among other
things, time lapse videos.

So like a good nerd I hacked one together using an
[arduino](http://www.arduino.cc/). It's about as simple as it gets. In my circuit
I used an infrared
<acronym title="Light Emitting Diode">LED</acronym> and that's it (Sure I should
have added a current limiting resistor, butI like throwing caution to the wind
sometimes). I found online someone who alreadyfigured out the blink code to
trigger a shutter release. I used his code and that was it!

<!--more-->

To test it I took it up to the top of
[Mt. Tabor](http://maps.google.com/?ie=UTF8&ll=45.511415,-122.593861&spn=0.013262,0.033023&z=16)
and snapped off a 8 second exposures continuously for almost an hour. Later
I took the results and used [blender](http://www.blender.org/) to stitch them
into a video. And here it is!

<div class="col-sm-12">
 <iframe src="//player.vimeo.com/video/8340328" width="600" height="356" frameborder="0"> </iframe>
</div>

[Portland at Night](http://vimeo.com/8340328) from [Nathan Bergey](http://vimeo.com/user574085) on [Vimeo](https://vimeo.com).

Notice that I caught the Hawthorne Bridge going up for a passing ship! Totally by accident.
