---
Title: Satellite Received!
tags:  radio sdr
---


At the local [hackerspace](http://makehackvoid.com) tonight, I finally received a morse beacon from a satellite! Hooray! It was FO-29, an Amateur Radio satellite. You can find the wav file (22.05 kHz, mono 16 bit) I recorded of its CW beacon, on 435.795MHz [here]({{ site_url}}/downloads/f029-20140226.wav).  The Morse is too fast for me to even translate it into dots and dashes! If you can keep up, please do let me know what it's saying!

This:

    <...._._.._..._.__._.....___._...>EI<......_.><ERR_15>L<......_..______...>
    <ERR_32><ERR_32><.............._____.............>E<ERR_32>IHSIII<ERR_6>
    IIIT<......_.><ERR_9> I<ERR_7><ERR_9><ERR_22><ERR_14>IF <.._....>C
    <_..._._...._._.><_........._..>H ENCN<.....__.><___._._>
    <.__.._._......_........__>GEER<...._..><....._>
    <......_..__....._...............>B<ERR_32><ERR_18><ERR_32>E<ERR_11>5I
    <ERR_7>5I<ERR_6><......_>EB IH <__._...._._.><_._..___.>
    <.__..._...._......>D<.._..._._._..__...._.__.._......><ERR_32><ERR_19>
    <ERR_32><ERR_29><ERR_21><ERR_32>EHIII EEOÜ<__.._.._><........_.....>
    <.___.....__><_._._><..____....._._.__....._.._.>I
    <.......__.......................>


is what multimon-ng makes of it. with similar output from fldigi.  Next time I'll set my filters a bit wider, or work out a better method of changing frequencies to keep up with the doppler shift.

To record the wav file, I used gqrx on my debian laptop, with a fc0012 + rtl2832u rtl-sdr dongle, then converted to mono at 22.05 kHz

My thanks go to [devdsp](https://github.com/devdsp) for holding the laptop and getting bitten by mosquitos while I pointed the [antenna]({% post_url 2014-02-02-Ardusat-contact-attempt1 %})!

