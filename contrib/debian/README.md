
Debian
====================
This directory contains files used to package wavid/wavi-qt
for Debian-based Linux systems. If you compile wavid/wavi-qt yourself, there are some useful files here.

## wavi: URI support ##


wavi-qt.desktop  (Gnome / Open Desktop)
To install:

	sudo desktop-file-install wavi-qt.desktop
	sudo update-desktop-database

If you build yourself, you will either need to modify the paths in
the .desktop file or copy or symlink your wavi-qt binary to `/usr/bin`
and the `../../share/pixmaps/wavi128.png` to `/usr/share/pixmaps`

wavi-qt.protocol (KDE)

