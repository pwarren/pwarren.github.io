---
Title: Lesson Learnt 001
tags:  amateur radio Beach40
---

Well, I finally collected all the extra bits I needed, and had an hour or two to proceed further with my Beach40 build, and got my recieve audio amplifier circuit built:

{% fancybox /images/beach40-2014-06-24.png 800x600 "Beach40 with audio circuit completed" %}

<!--more-->

The more experienced of you can probably see exactly what I've done wrong there.  That photo is from after I'd removed the broken bits!

The lesson I learnt was, always double check the pinout of your chip :)  I had thought the pins were numbered down each side, but they are in fact numbered in a circular fasion.  So I had +12V going in to the audio out pin of the lm386.

Needless to say, this didn't end well! The input voltage resistor went pop, started glowing white, and let out the magic smoke, there's also some damage to the packaging of the lm386 chip.

Luckily I have a spare lm386 in my junque box, so I'll stick that in tomorrow, and see how I go!