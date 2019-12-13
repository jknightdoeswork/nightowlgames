---
layout: page
title: hyperputt
permalink: /hyperputt/
---

_Last updated: December 12th, 2019_

_Note: this page is in development._

HyperPutt is an elegant golf puzzle game being developed in the Godot Engine.

![hyperputt-cliffhanger][cliffhanger]  
_My first level, December 4th, 2019_

HyperPutt aims to be a zen puzzler. I'm working hard to make the levels interesting and challenging. I hope to release HyperPutt in mid 2020 on Steam, Google Play and the iOS App Store.

![hyperputt-waterfall][waterfall]  
_A waterfall, a wiggling flag & a rotatable camera December 11th, 2019_

Progress has been slow but steady. I'm focusing on trying to create scenes that will immediately capture attention. It takes time to iterate on every piece. I know I have a long way to go.  


![hyperputt-waterfall2][waterfall2]  
_Trying to make a better waterfall, December 12th, 2019_

I spent a few hours experimenting with different values on the water and waterfalls. These are much more performant values (I shrank the noise textures). I think the water looks pretty good, but I think the waterfall could use some improvement still. I also changed the direction of the light, just as an experiment.

![hyperputt-waterfall3][waterfall3]  
_Another few hours of iteration on the water, December 12th, 2019_

Woah. This is getting close. I got this effect by cranking up the x value on the displacement map on the waterfall. This has the effect of "smearing" the noise blobs horizontally across the waterfall into a line. It's getting close to reaching the quality bar that I'm aiming for.

![hyperputt-waterfall4][waterfall4]  
_I can finally move on, December 12th, 2019_

I've tweaked some numbers, and have reached a waterfall effect that I'm happy with. I made the particles smaller, I brightened up the whole level a bit, and I adjusted the noise on the waterfall to not be so chaotic.

[cliffhanger]:{{site.baseurl}}/assets/img/hyperput_cliffhanger.gif "HyperPutt Gif"
[waterfall]:{{site.baseurl}}/assets/img/hyperputt_flagwiggle3.gif "HyperPutt Waterfall"
[waterfall2]:{{site.baseurl}}/assets/img/hyperputt_waterfall6.gif "HyperPutt Waterfall2"
[waterfall3]:{{site.baseurl}}/assets/img/hyperputt_waterfall7.gif "HyperPutt Waterfall3"
[waterfall4]:{{site.baseurl}}/assets/img/hyperputt_waterfall10.gif "HyperPutt Waterfall4"