README xorg-server


WARNING
=======

If you fail to rebuild input and video packages for xorg-server on major ABI
changes, eg. 1.16.0 -> 1.17.0.  You will end up with no mouse or keyboard and
possibly no direct 3D acceleration for video.

If you do happen to forget and have sys-rq enabled in your kernel you can do a
safe reboot with holding down Alt + SysRq, and typing the following sequence
in order, pausing for several seconds between each key:

	reisub


POST-INSTALL
============

After upgrading xorg-server, from major versions rebuild video and input
packages:

NOTE: This only applies on ABI changes between major versions e.g.  1.16.0 ->
1.17.0.

	sudo pkgman update -fr $(pkgman list --regex \
		--filter='^xorg-xf86-(input|video)|^mesa')

If you use nvidia you also need to do this:

	sudo gl-select use xorg  &&  sudo gl-select use nvidia


End of file.
