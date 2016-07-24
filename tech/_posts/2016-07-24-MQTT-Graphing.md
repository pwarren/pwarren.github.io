---
Title: Back Again!
date: 2016-07-24 21:45:00
tags: tech
---

Having attended the LCA2016 [OpenHardware miniconf](http://www.openhardwareconf.org/wiki/Main_Page) I have an [ESPlant](https://github.com/CCHS-Melbourne/ESPlant) module, and it had just sat in it's packet since the conference in February!

I finally got it hacked together to do some data collection!  I used mosquitto on my in home debian server to be the broker, which mqtt2rrd then listens on for the MQTT messages, and spits out some RRD files. Finally, drraw.cgi on my internal web server creates the graphs on the fly!

{% fancybox left medium /images/2016-07-24-ESPlant.png "Temp, Humidity, Pressure and Voltage graphs in drraw.cgi" %}

I've put it in our north facing bedroom, with the solar panel stuck on the window, so hopefully it'll charge enough during the day to measure constantly.

I may have to look at @projectgus' firmware that does longer sleeping.

A good afternoon's hacking I reckon!