---
Title: OCF Diploe Up!
tags: tech amateur radio 
---

I've managed to string up an 80m Off Centre Fed Dipole over the weekend, I managed a contact to Kentucky, USA, on 20m, and got a 59 report with my 100W and his gigantic yagi of doom! Also had a half dozen SOTA contacts on 40m and 20m over Sunday afternoon, so it's fair to say it works!

I had taken some photos, but it's actually really hard to see it in them! It's just some wires running through the trees.

Last night I spent some time with the local club's MFJ analyser (Thanks Gilbert!) and got an SWR graph of the antenna as installed:

{% fancybox /images/ocf_swr.png 1024x768 "80m Off Centre Fed Dipole SWR vs Frequency" %}

<!--more-->

Spreadsheet available on [google drive](https://docs.google.com/spreadsheets/d/1HkWkwKKXdAVkZsj5o_kiEOkqZ5DnnjBpoTTgiWST81U/edit?usp=sharing).

 Salient points:
Lowest frequency minimum SWR: 1.9 @ 3.455MHz

Other minimums:
* 1.8 @ 7.133 MHz
* 1.2 @ 14.494 MHz
* 1.4 @ 18.046 MHz
* 1.3 @ 25.252 MHz
* 1.5 @ 29.006 MHz

Is that telling me I should shorten it a touch, to get the lowest frequency dip up into the 80m band a bit more?

I'm running my Kenwood TS-140S to it through an MFJ 986 manual tuner, which is able to get it to 1:1 SWR on 80, 40 20, 17, 12 and 10m without much difficulty, so I may just leave it as is!

I Haven't tried 15 and 30m yet, is that going to be possible?

I'd also managed to put a station ground in a few weekends ago, which has reduced the RFI to my PC's audio system, but, my house alarm still goes off if I try any mode other than SSB voice.  FM, AM and JT65 modes, will set it off at varying power levels, FM and AM only at full output power, nominally 50W, and JT65, even at 10W.

I'm told there are a few options to attempt remedying this:
* Put common mode chokes on the wires of the alarm system that go to the various devices around the house, 10 turns around one or two t130-2s
* Put capacitors between the signal wire and the alarm board
* replace cables with screened ones.

Having further thoughts, it may be 433MHz reciever for the key fobs being overloaded, as you can set off the lights and sirens by pressing all the buttons on the fob, and from the keypad, but it's a special mode, not set off by sensors.

May have to ring the installer, see if he's got any tips!
