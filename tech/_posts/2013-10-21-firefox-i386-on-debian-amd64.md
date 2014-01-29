---
title: "Firefox i386 on Debian amd64"
tags: open-source tech
description: "How I got proper firefox running on Debian"
---

Goto http://getfirefox.com/ and download the latest one.

     tar -jxvf firefox-*.tar.bz2
     sudo mv firefox /opt
     sudo dpkg --add-architecture i386
     sudo apt-get update

     sudo apt-get install libc6:i386 libstdc++6:i386 libxrender1:i386 libasound2:i386 libdbus-glib-1-2:i386 libxext6:i386 libgtk2.0-0:i386 libxt6:i386 libcurl3:i386 libnss3:i386 libnspr4:i386 libssl1.0.0:i386

After that,

      /opt/firefox/firefox
      should work.

Next get the 32 bit tar.gz file for adobe flash, unpack and copy it to /opt/firefox/browser/plugins/

     tar -zxvf install_flash_player_11_linux.i386.tar.gz
     mkdir -p /opt/firefox/browser/plugins

     cp libflashplayer.so /opt/firefox/browser/plugins

and you should be good to go!
