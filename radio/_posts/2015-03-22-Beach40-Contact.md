---
title: Beach 40 Contact and general radio update!
tags: Beach40 Amateur Radio
---
Over the last few weeks I've debugged my Beach40 a bit! I found that I'd stuck in the wrong size resistor on the lm386 feedback circuit, 2.2 Ohms, vs the needed 2.2 kilo-Ohms! So, with that fixed, it worked a bit better!

{% fancybox right large /images/2015-03-22-Beach40-Setup.jpg "Beach40 as set for a QSO, and a messy desk! http://openradio.net.au board in the background" %}

Audio was still rather low, so I added in the BC548 RF pre-amp, which boosted the signal up very well, can get too loud now with the headphones on! Unfortunately, it had the side effect of increasing the AM broadcast break-in, meaning I could hear Radio National across the dial!

So, I built a high pass filter, and stick that inline to the Beach40.  I had put one internally to start with, but it functioned more as an attenuator, than a filter!  Now that I've built one that works, I might try to integrate it into the case.

And, now I've finally had a contact with it!  VK1DA was activating the local repeater site for SOTA, and I managed to get a 3x2 report from him with the radio, which was a bit lower than I thought I should get. Putting it on the dummy load, the scope is seeing ~5V peak to peak, which may be a bit lower than expected, might check the resistors in the RF amplification stage, see if I got any of those wrong!

Yay, my first home brew radio success, very pleased with myself :)

As a learning experience, I've been putting my Beach40 circuit into [KiCAD](http://kicad.org), and you can find all the work I've done, at my [Git Hub](https://github.com/pwarren/electronics/). I did have plans of doing an all SMT layout for the board, but I think I'll save that for my next challenge, an SSB home-brew rig!

I'll be looking at the "Let's Build Something" series from Pete, N6QW, details on [his website](http://jessystems.com/LBS_Detail.htm). I already had a few of the bits, and have since bought a bunch more! Hope to have the Part 1 bits done this week, to get me a direct conversion receiver done!

I've been [hacking](https://github.com/pwarren/Si5351Sketches) away at the arduino code for the Si5351 clock chip that the design uses for a VFO and BFO, I have it mostly working with the [Freetronics](http://freetronics.com.au) LCD board and their 'eleven' and arduino uno clone.  I have some rotary encoders, now, so that should progress eventually!  Lots to do!
