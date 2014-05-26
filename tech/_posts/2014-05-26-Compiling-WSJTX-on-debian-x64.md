---
Title: Compiling WSJTX on debian
date: 2014-05-26 16:45:00
tags: tech amateur radio
---

    dpkg -add-architecture i386
    
    sudo apt-get install  gcc g++ gfortran make libfftw3-dev \
    libpulse-dev libhamlib-dev qtbase5-dev  pulseaudio subversion \
    libgfortran3:i386 libc6-i386 libqt5multimedia5-plugins \
    qtmultimedia5-dev
    
    svn co svn://svn.berlios.de/wsjt/branches/wsjtx
    
    cd wsjtx
    
    mkdir build
    
    cd wsjtx
    
    cmake ../
    
    make -j4
    
    cp ../*.dat ../*.txt ./
    
    cp -R ../Palettes ../samples ./
    
    chmod +x contrib/kvasd
    
    ln -s lib/jt9 ./
    
    ./wsjtx

