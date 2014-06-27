---
title: Attempt No.1 to receive Ardusat
tags: tech ham antenna
---


Today, I built an antenna as specified here:

http://forums.snapstream.com/vb/showthread.php?t=38708


here's what my version looks like:


{% fancybox /images/433MHz_yagi_post.jpg "433 MHz Yagi Antenna" %}


I attempted to receive ArduSat-X and ArduSat-1, and I think I saw the CW beacon of ArduSat-X with [gqrx](http://gqrx.de) but I hadn't adjusted for the doppler effect, or something, because it appeared some distance away from 437.000MHz. And I only recorded the last few symbols, not even a full letter of morse.

Over the next little while, I'll try to construct a flow graph in GnuRadio that'll let me see the FFT waterfall, hear where I'm tuned to, and record the raw IQ values for the whole range, so I can come back later and decode the FM CW beacon at the corrected location!