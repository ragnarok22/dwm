# Ragnarok's dwm configuration
dwm is an extremely fast, small, and dynamic window manager for X.

## Requirements
In order to build dwm you need the Xlib header files.

## Installation
Edit config.mk to match your local setup (dwm is installed into
the /usr/local namespace by default).

Afterwards enter the following command to build and install dwm (if
necessary as root):

    make clean install

## Running dwm
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

## Patches and features
- [alpha](https://dwm.suckless.org/patches/alpha/) - adds transparency to the bar and windows
- [alwayscenter](https://dwm.suckless.org/patches/alwayscenter/) - centers windows when they are created in floating mode
- [attachbottom](https://dwm.suckless.org/patches/attachbottom/) - new clients attach at the bottom of the stack
- [fibonacci](https://dwm.suckless.org/patches/fibonacci/) - adds fibonacci layout
- [hide vacant tags](https://dwm.suckless.org/patches/hide_vacant_tags/) - hides tags with no clients
- [movestack](https://dwm.suckless.org/patches/movestack/) - move clients around in the stack and swap them with the master
- [pertag](https://dwm.suckless.org/patches/pertag/) - maintains layout and mwfact per tag
- [splitstatus](https://dwm.suckless.org/patches/splitstatus/) - replaces the standard statusbar items with two status items: one in the centre, and one on the right.
- [uselessgap](https://dwm.suckless.org/patches/uselessgap/) - adds "useless gaps" around windows
- [warp](https://dwm.suckless.org/patches/warp/) - warps the mouse pointer to the center of the focused window when switching tags

## Configuration
The configuration of dwm is done by creating a custom config.h
and (re)compiling the source code.
