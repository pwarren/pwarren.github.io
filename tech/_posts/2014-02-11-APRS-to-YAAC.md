---
title: APRS from RTL-SDR shown in YAAC
tags: tech sdr radio aprs aprs-is
---

Today I figured out how to get APRS packets shown on a map with [Yet Another APRS Client](http://www.findtheater.com/ka2ddo/YAAC.html).

First up start up rtl_fm and pipe it to multimon-ng:

      rtl_fm -f 145.1717M -s 22050 | multimon-ng -q -A -a AFSK1200 -t raw - > aprs.txt

I had to adjust the frequency to correct for my dongle's innacuracy, in my location APRS is at 145.175MHz, using the various tools to determine its PPM error did not help, as adding the -p flag to rtl_fm did nothing.  To get the proper frequency I used [gqrx](http://gqrx.de), the best, actually open source SDR viewing tool out there, to see where the signals were centred according to the Dongle.

I pipe it to a file so I've got a nice lot of packets to test things with. Multimon puts out lines like:


       APRS: VK2RTZ-1>APNU19,VK2AMW-1*,VK1RGI-1*,WIDE2*:!3256.46SS15130.90E#PHG4430/W2 Digi Mt Sugarloaf
       APRS: VK2TGB-7>S3T2W3,VK2AMW-1*,VK1RGI-1*,WIDE2*:`N?:l+o>/
       APRS: VK2HLT-8>S5P8Q1,VK2RWG-1*,VK1RGI-1*,WIDE2-1:'K/il"-j/]"69}Pathfinding R51
       APRS: VK2AMW-1>APNU19,VK1RGI-1*,WIDE2*:!3433.21SS15037.76E# W2 Digi  Knight's  Hill
       APRS: VK2RGN-1>APOT30,VK1RGI-1*,WIDE2*:!3445.39S/14941.30E#Goulburn - Echo/IRLP on 147.925 VK2RGN
       APRS: VK2HLT-8>S5P8Q1,VK2RWG-1*,VK1RGI-1*,WIDE2-1:'K/il"-j/]"6?}Pathfinding R51


Which is not quite what YAAC is expecting, it likes things to be in APRS-IS format, which multimon almost does, just need to remove the "APRS: " characters from the start, colrm or cut should do the trick. Then pipe that output to netcat, so that YAAC can read it! I had thought that the -q (quiet) flag would do that, but alas, that just omits the copyright notice and available decoders.


      inotail -f aprs.txt | stdbuf -oL cut -c 7- | nc -l 14580


I had to use inotail and stdbuf as with this many pipes, and small data volumes, pipes don't get flushed enough for it to work properly. I'll make a small python script eventually that'll emulate a APRS-IS server so that a number of clients could connect to it.

Finally, within YAAC create a new APRS-IS 'port' that points to your sever, and watch the packets get displayed!  Similarly, anything that can read APRS-IS should be able to read from the netcat port. Beware, netcat doesn't keep going after you quit, you'll have to restart it again.


I'm pretty sure you could do something like:

      rtl_fm -f 145.1717M -s 22050 | multimon-ng -q -A -a AFSK1200 -t raw - | stdbuf -oL cut -c 7- | nc -l 14580

and omit the aprs.txt file, but I've not tried it.  Hope that's useful.