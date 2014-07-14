---
Title: Beach40 Finished!
tags: tech amateur radio Beach40
---

Had a bit of a quiet weekend, didn't get a huge amount of radio stuff done, instead mostly housework, looking after the kids and on call work!

However, I got my dummy load built:

{% fancybox /images/qrp_dummyload.png 800x600 "Homebrew QRP dummy load" %}

<!--more-->

It's 1.0 SWR from 1.5MHz until about 6MHz, then 1.1 until 12MHz, then 1.3 until 18Mhz, 1.5 at 27MHz, and then stays there until about 70Mhz where it jumps to 2.0.  Theres a dip down to 1.2 at ~110MHz, then back up to 2.0 by 120MHz and stays there until 155Mhz, which s the limit of the analyser I'm borrowing. Yes, I'll shorten that lead to the signal side of the board!

So, it should be good for testing my beach40, and other bits that I build! I used 44 * 2k2 Ohm 1/2 watt resistors. It measures 51.3 Ohms across them with my cheapo jaycar multimeter, and should be able to dissapate 10 watts easily, dont' think I'll try putting 20W through it!

I don't think I have the detector right yet, there are various designs around the web, and I'll have to keep tinkering to see what works!

Also made a start on the enclosure for my Beach40, it's an old PC power supply box.

{% fancybox /images/beach40_enclosure.png 800x600 "Homebrew QRP dummy load" %}

I've trimmed the board I built the beach40 on to fit, and it's nice and snug, will have to figure out mounting. I think double sided tape will be the go!

I pulled out the PSU PCB and discovered why it didn't work, one of the resistors had carbonised! But there are some nice components on it for the junque box, some nice big toroids and capacitors, a bunch of 12v regulators with heatsinks and a couple of transformers.  

There's some slots in one side where the modular power cables came out, which are a pretty good fit for the antenna ports. I'll be spending this week fitting on the connectors and working out how to mount the PCB. Then final TX adjustment on the dummy load, and hook up to it's end-fed antenna to see if reception is Ok.
