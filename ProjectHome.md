## Introduction ##
This is a student project in [EE 382N-4](http://users.ece.utexas.edu/~mcdermot/ee382n_fall_2009.htm) (Advanced Embedded Systems Architecture) in Fall 2009 in the University of Texas at Austin. Project members are Hui Chen and Keji Ren.

We achieved a **three-second boot**. Boot time is defined as the delay from turning on power to a shell welcome prompt (or a GUI).

Please keep in mind all optimizations may only be applied to the reversion C board.

## Where to start ##

1. Please read [our slides](http://swiftbeagle.googlecode.com/files/beagleboard_project_hui_keji.pdf)  to have a general idea on the techniques we used to achieve fast boot.

2. Read on [how to compile our modified code](http://code.google.com/p/swiftbeagle/wiki/how_to_compile_bootloader_n_kernel) if you want to compile x-loader, u-boot, kernel and rootfs from source code.

3. Or just download whatever you need from [download page](http://code.google.com/p/swiftbeagle/downloads/list).

4. This [wiki page](http://code.google.com/p/swiftbeagle/wiki/upload_binary_to_nand_mmc) may help you upload binaries to NAND and MMC.

Please also have a look in the [project wiki](http://code.google.com/p/swiftbeagle/w/list) for more information. [Open a ticket](http://code.google.com/p/swiftbeagle/issues/list) to us if you still have questions but we make no promise in solving your problem.

## References ##

**hardwares**
  1. [Homepage](http://beagleboard.org/) of beagleboard
  1. Texas Instrument's [OMAP 35x wiki pages](http://wiki.omap.com/index.php/Category:OMAP35x)
  1. Beagleboard rC3 [manual](http://beagleboard.org/static/BBSRM_latest.pdf). rC3 beagleboard is the version we used in our project.
  1. Beagleboard's [NAND partition](http://elinux.org/BeagleBoardNAND)

**softwares**
  1. [Beagleboard page](http://elinux.org/BeagleBoard) on elinux.org
  1. [CodeSourcery GNU C compiler](http://www.codesourcery.com/sgpp/lite/arm/) is the toolchain we used
  1. We use [uclibc](http://www.uclibc.org) as our lightweight C library.

**kernel and bootloader**
  1. [Method](http://elinux.org/BeagleBoardLinuxKernel) to compile customized kernel for bb
  1. [U-boot homepage](http://www.denx.de/wiki/U-Boot)

**fast boot**
  1. [This page on elinux.org](http://elinux.org/Boot_Time) gave a good coverage of technologies to achieve fast boot
  1. [Methods](http://elinux.org/Suspend_To_Disk_For_ARM) to suspend system (to disk) were covered