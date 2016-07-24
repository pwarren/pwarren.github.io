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

### Details

The standard mosqitto package on debian 7 doesn't cope with the ESPlant's output, so I installed from the [github](https://github.com/eclipse/mosquitto)repo, and to keep things 'easy', moved the distro binary to a backup file, and linked /usr/local/sbin/mosqitto in to /usr/sbin. No config changes necessary!

On my web server VM, I cloned [MQTT2RRD](https://github.com/irvined1982/MQTT2RRD). I had to install the python-mosqitto and python-rrdtool packages, but after that it worked fine!  For it's config I'm sticking the RRD files on my NAS. I'm not sure if the 'archives' bit is doing what I think it is, but time will tell I suppose!

{% highlight kconfig %}
[daemon]
data_dir = /media/media/mqtt
pid_file = /tmp/mqtt2rrd.pid
user = pwarren
group = pwarren

[logging]
log_file = /tmp/mqtt2rrd.log
log_level = 30

[mqtt]
client_id = "Ashpool"
hostname = ashpool.lan
port= 1883
#username="bob"
#password="t0ps3cr3t!"
keepalive=60
subscriptions=#

[/ESP_b5952/temp/c]
friendly_name = "Temperature"
step=30
archives=RRA:AVERAGE:0.5:1:120,RRA:AVERAGE:0.5:5:288

[/ESP_b5952/pressure_mbar]
friendly_name = "Atmospheric Pressure"
step=30
archives=RRA:AVERAGE:0.5:1:120,RRA:AVERAGE:0.5:5:288
{% endhighlight %}

Lastly, I installed drraw from apt, it's config was rather simple to start with, point it to the RRD files, and get apache to serve up /cgi-bin/drraw/drraw.cgi and go nuts creating graphs and dashboards!