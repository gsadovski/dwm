
# dwm - dynamic window manager
dwm is an extremely fast, small, and dynamic window manager for X.


# Requirements
In order to build dwm you need the Xlib header files.


# Installation
Edit config.mk to match your local setup (dwm is installed into
the /usr/local namespace by default).

Afterwards enter the following command to build and install dwm (if
necessary as root):

    make clean install

If you are going to use the default bluegray color scheme it is highly
recommended to also install the bluegray files shipped in the dextra package.


# Running dwm
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


# Configuration
The configuration of dwm is done by creating a custom config.h
and (re)compiling the source code. The modification to config.h were:

1. topbar variable set to 0, which means that the menu bar is now at the bottom;
2. font and dmenufont changed to Inconsolata;
3. Solarized color scheme added. Here the dwm.c file was modified so that the status bar now has the SchemeSel colors as defined in config.h;
4. No special rules for apps like Firefox and Gimp;
5. mfact set to 0.5. Now master and slave area divide the screen in exactly half;
6. resizehints was set to 0. This is a workaroud to prevent terminal emulator windows to have useless gaps in tile stack mode of slave area;
7. MODKEY altered to MOD4Mask (windows key in the keyboard). Now win key instead of alt is used as the main key modifier;
8. Fibonacci patch was added. The layout dwindle was set as the default one and the hotkeys MODKEY+s and MODKEY+\ were attributed to the spiral and dwindle layout, respectively;
9. fakefullscreen patch added;
10. noborder patch added;
11. fancybar patch added;
12. movestack patch added;
13. pertag patch added;
14. attachaside patch added.
