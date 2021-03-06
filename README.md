dwm - dynamic window manager
============================
dwm is an extremely fast, small, and dynamic window manager for X.

Version
-------
This repo is based off of DWM version 6.1.
In particular, see [this commit](https://git.suckless.org/dwm/commit/b69c870a3076d78ab595ed1cd4b41cf6b03b2610.html).

See the original source [here](https://dwm.suckless.org/).

Patches I've added
------------------
* [systray](https://dwm.suckless.org/patches/systray/)
* [uselessgap](https://dwm.suckless.org/patches/uselessgap/)
* [hide vacant tags](https://dwm.suckless.org/patches/hide_vacant_tags/)
* I've updated the function `incnmaster` to maintain at least one master window. This prevents wraparound when decrementing the number of master windows.

See `config.def.h` for color settings, font sizes, etc.

Keybindings are set in `keys.h`.
An example config file is found in `keys.h.example`.
To build, you'll need to copy this over to `keys.h`.

Similar to the keybindings, colors are set in `colors.h`.
An example config file is found in `colors.h.example`.

Requirements
------------
In order to build dwm you need the Xlib header files.


Installation
------------
Edit config.mk to match your local setup (dwm is installed into
the /usr/local namespace by default).

Afterwards enter the following command to build and install dwm (if
necessary as root):

    make clean install


Running dwm
-----------
Add the following line to your .xinitrc to start dwm using startx:

    exec dwm

In order to connect dwm to a specific display, make sure that
the DISPLAY environment variable is set correctly, e.g.:

    DISPLAY=foo.bar:1 exec dwm

(This will start dwm on display :1 of the host foo.bar.)

In order to display status info in the bar, you can do something
like this in your .xinitrc:

    while xsetroot -name "`date` `uptime | sed 's/.*,//'`"
    do
    	sleep 1
    done &
    exec dwm


Configuration
-------------
The configuration of dwm is done by creating a custom config.h
and (re)compiling the source code.
