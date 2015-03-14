If you don't want to compile from source, use the compiled binaries from the [download page](http://code.google.com/p/swiftbeagle/downloads/list).

You need a toolchain to compile code for arm processor. I recommend [the one](http://www.codesourcery.com/sgpp/lite/arm/) from Code Sourcery (choose the GNU/Linux version in download page). I used the 2009-q1 version since the q3 version may have [a defect](http://code.google.com/p/swiftbeagle/wiki/sourcery_toolchain).

## signGP ##

Enter the directory and

```
gcc signGP.c -o signGP
```

You will need signGP to sign x-load.bin.

## x-loader ##

Enter the directory and

```
$ make omap3530beagle_config
$ make 
$ ./signGP x-load.bin
```

x-load.bin.ift will be generated. The difference between x-load.bin and x-load.bin.ift is the latter has an additional 8-byte header to tell how large x-load.bin is.

## u-boot ##

Enter the directory and

```
$ make omap3_beagle_config
$ make
```

u-boot.bin will be generated under the directory.

## Linux Kernel ##

Enter the kernel directory and

```
$ copy my.config .config
$ make uImage
```

If you have muti-core processor, using 'make uImage -j n' (n is the number of CPU cores) will speed up the compilation a lot. uImage will be under arch/arm/boot/ directory.

## uclibc and busybox ##

Enter the buildroot directory and

```
$ make menuconfig
$ make
```

will generate the toolchain you need. Copy uClibc.config to toolchain\_build\_arm/uclibc\_xxx directory and change name to .config. Copy busybox.config to project\_build\_arm/uclibc/busybox\_xxx directory and change name to .config. Then in the buildroot directory issue

```
$ make uclibc-clean
$ make uclibc
$ make busybox-clean
$ make busybox
```

Your rootfs (with uclibc and busybox) will be under project\_build\_arm/uclibc/root directory.