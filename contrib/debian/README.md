
Debian
====================
This directory contains files used to package coinclixd/coinclix-qt
for Debian-based Linux systems. If you compile coinclixd/coinclix-qt yourself, there are some useful files here.

## coinclix: URI support ##


coinclix-qt.desktop  (Gnome / Open Desktop)
To install:

	sudo desktop-file-install coinclix-qt.desktop
	sudo update-desktop-database

If you build yourself, you will either need to modify the paths in
the .desktop file or copy or symlink your coinclixqt binary to `/usr/bin`
and the `../../share/pixmaps/coinclix128.png` to `/usr/share/pixmaps`

coinclix-qt.protocol (KDE)

