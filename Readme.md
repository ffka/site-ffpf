Freifunk Pforzheim gluon config
===========================

How To Build
------------

This is building FFPF firmware in a nutshell. For more on options or building specific branches please refer to [the official Gluon repository](https://github.com/freifunk-gluon/gluon) at GitHub, or [the official Gluon documentation](http://gluon.readthedocs.org/).

To compile the firmware you need a working build environment and packages for git, subversion, gawk, unzip, ncurses headers and zlib headers.

On Debian GNU/Linux, install like this:

    sudo apt-get install git subversion python build-essential gawk unzip libz-dev libncurses-dev libssl-dev

To avoid weird build errors it is recomended to link the /bin/sh to bash. Debian uses per default the dash 
    
    ln -snf /bin/bash /bin/sh

Then download and build as follows:

    git clone git://github.com/freifunk-gluon/gluon.git         # Get the official Gluon repository
    cd gluon
    git clone https://github.com/ffka/site-ffpf site   			# Get the Freifunk Pforzheim site repository
    make update                                                 # Fetch all repositories
    make DEFAULT_GLUON_RELEASE=<release number> GLUON_TARGET=ar71xx-generic 

with make without any options you will get a list of all available GLUON_TARGETS you can use. 


**Note** you will need about 10 GB disk space per build target.
