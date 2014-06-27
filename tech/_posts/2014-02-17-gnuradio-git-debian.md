---
title: Building GnuRadio from git on Debian 7
tags: tech yakshaving gnuradio debian libice
---

Okay, so in order to play with some new blocks I found, [gr-rds] (https://github.com/argilo/gr-rds) in particular. It appears I needed a newer version of gnuradio than I had previously built from git to get the Control Port functions these blocks require.

So, off I go and

    git pull
    cd build
    rm -rf *
    cmake ../
    make

and get:

    /usr/include/c++/4.7/bits/stl_tree.h:646:9:   required from ‘std::_Rb_tree<_Key, _Val, _KeyOfValue, _Compare, _Alloc>::~_Rb_tree() [with _Key = int; _Val = std::pair<const int, IceInternal::Handle<Ice::Object> >; _KeyOfValue = std::_Select1st<std::pair<const int, IceInternal::Handle<Ice::Object> > >; _Compare = std::less<int>; _Alloc = std::allocator<std::pair<const int, IceInternal::Handle<Ice::Object> > >]’
    /usr/include/c++/4.7/bits/stl_map.h:90:11:   required from here
    /usr/include/Ice/Handle.h:106:13: error: ‘upCast’ was not declared in this scope, and no declarations were found by argument-dependent lookup at the point of instantiation [-fpermissive]
    In file included from /usr/include/Ice/Ice.h:30:0,
                 from /home/alc/sdr/gnuradio/v3.6.4.1-946-g7f0d3777-next/gnuradio-core/src/lib/runtime/ice_application_base.h:28,
                 from /home/alc/sdr/gnuradio/v3.6.4.1-946-g7f0d3777-next/gnuradio-core/src/lib/runtime/ice_application_base.cc:23:
		 /usr/include/Ice/Connection.h:92:29: note: ‘Ice::LocalObject* IceInternal::upCast(Ice::UDPConnectionInfo*)’ declared here, later in the translation unit
		 make[2]: *** [gnuradio-core/src/lib/CMakeFiles/gnuradio-core.dir/runtime/ice_application_base.cc.o] Error 1
		 make[1]: *** [gnuradio-core/src/lib/CMakeFiles/gnuradio-core.dir/all] Error 2
		 make: *** [all] Error 2

Apparently, the debian build of ZeroC's Ice lib is bad, simple enough to fix, if you don't mind stuff accumulating in /usr/local! Go to [ZeroC's source download site](http://www.zeroc.com/download.html#src) and grab the latest tarball, unpack it.

I edited the cpp/conf/Make.rules to install to /usr/local/, change as you see fit, or leave it at the default.


Then gnuradio builds fine again!