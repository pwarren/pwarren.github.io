---
Title: OzQRP MST2 20m build log, day Something
tags: tech electronics buildlog MST2 amateur radio
---

Well, after getting my MST2 in an enclosure and looking Ok:

{% fancybox /images/MST2_20m_box.jpg 800 600 "OzQRP MST2 20m in an enclosure" %}

I went to a friendly ham's workshop and started aligning it.  The receive slug tuning and mixer balancing went perfectly well. When we got to doing the transmit tuning, things started to go a bit skee-whiff! The MST2 turned off.  So we replaced the fuse, which promptly blew, and another!

After turning the PA bias and mic gain down, and unshorting the PTT line and trying another fuse the magic smoke came out of the MOSFET!

We then tested the audio generator, and it was putting out 1v peak to peak, instaed of the 50mV we'd set it to, so we figure the MOSFET was being overdriven for a significant period of time (10 minutes or so!), and decided it had had enough of that, and gave up the ghost :(

{% fancybox /images/MST2_20m_blown_final.jpg 800 600 "Aftermath of Magic Smoke(tm) escape" %}

So, now to find a source of IRF510 MOSFETs!