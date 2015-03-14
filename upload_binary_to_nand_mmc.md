## Prerequisite ##

You should have other working versions of x-loader and u-boot installed on your BeagleBoard. If you don't, follow the [official instruction](http://code.google.com/p/beagleboard/wiki/BeagleboardRevCValidation) to have them.

You should have an SD card in FAT32 format. If you have multiple partitions on the SD, make sure the first one is in FAT32.

## x-load, u-boot and kernel ##

Copy x-load.bin.ift, u-boot.bin and uImage to the FAT32 partition.

Follow this [good article](http://elinux.org/BeagleBoardNAND) on eLinux.org to write x-loader, u-boot and Kernel to NAND. Note: you may not need the 'nand unlock' if you are using a new version of u-boot.

## Linux rootfs ##

The Linux partition must be the second partition on SD (aka /dev/mmcblk0p2) and its format must be EXT2. Remove everything in the EXT2 partition, uncompress the rootdisk.tar.gz you download from the [download page](http://code.google.com/p/swiftbeagle/downloads/list) (or you compiled) and copy everything to the EXT2 partition's root directory. Make sure you use 'cp -avrf' option to preserve links and device nodes.

You may want to remove /linuxrc, /etc/inittab and /etc/init.d/`*` (but keep the /etc/init.d/rcS!) to make boot faster.

Umount the drive and you are done.