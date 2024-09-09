Open Sound Meter is a FFT based application for tuning sound systems.

It's main author is Pavel Smokotnin, the project page lives at
https://opensoundmeter.com/ and the source code repository is on
github: https://github.com/psmokotnin/osm

This is a PKGBUILD for the Archlinux (I'm using Arch, by the way!)
package manager.

Opensoundmeter is normally distributed as an appimage, but as I
prefer native builds, I've written this PKGBUILD.

How to use:

 (1) obtain this PKGBUILD and the associated patches,
     put them into one directory, e.g by cloning this git repo.

	$ git clone https://github.com/vogelchr/opensoundmeter_pkgbuild.git
	$ cd opensoundmeter_pkgbuild

 (2) build the package by running "makepkg"

	$ makepkg
	==> Making package: opensoundmeter 1.3-1 (Mo 09 Sep 2024 22:21:03 CEST)
	==> Checking runtime dependencies...
	==> Checking buildtime dependencies...
	==> Retrieving sources...
	  -> Cloning osm git repo...
	(...)
	==> Leaving fakeroot environment.
	==> Finished making: opensoundmeter 1.3-1 (Mo 09 Sep 2024 22:25:24 CEST)

     two package files should have been created...

	$ ls -l
	(...)
	-rw-r--r-- 1 chris users 12781804  9. Sep 22:24 opensoundmeter-1.3-1-x86_64.pkg.tar.zst
	-rw-r--r-- 1 chris users 28963371  9. Sep 22:25 opensoundmeter-debug-1.3-1-x86_64.pkg.tar.zst

     One is the actual application, the other is part of the sourcecode, for debugging purposes.

  (3) you can now install the application

	$ sudo pacman -U opensoundmeter-1.3-1-x86_64.pkg.tar.zst

  (4) The application should now be installed and visible in your desktop environment of
      choice in the "Multimedia" category.


