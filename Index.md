

# jz soc #


&lt;hr&gt;


## Introduction ##

Jz4740 is a multimedia application processor targeting for mobie devices like smart-phone,PMP and GPS.Incorporate the XBurst CPU core based on leading micro-architecture technology, this processor provides high integration,high performance and low power consumption solution for embedded device.

Jz4720 is the die of Jz4740. It is a low cost multimedia application processor targeting for mobile devices like MP4, electronic dictionary.

JZ4732 is same to JZ4740 and it is for oversea customers.

## usb boot ##

JZ4740 can be booted form USB. If so, the internal ROM can communicate with PC using USB port. PC can send files to JZ4740's internal ram or SDRAM and execute program.

## nand boot ##

JZ4740 can boot from nand flash devices. If it is configured booting from nand flash, its internal rom load the first 8K code from nand flash into internal sram and then execute. This 8K code can contain SDRAM init process and other low level init functions and then the program can be executed in SDRAM.

# source code from jz #


&lt;hr&gt;


Ingenic has released the source code of u-boot/linux kernel and busybox.

## toolchain ##

### linux 2.6 ###
  * [gcc-4.1.2 binary  version for linux](ftp://ftp.ingenic.cn/3sw/01linux/00toolchain/mipseltools-gcc412-lnx26.tar.gz)

  * [gcc-4.1.2 toolchain source code](ftp://ftp.ingenic.cn/3sw/01linux/00toolchain/jz-gcc412-glib236-src.tar.gz)

Follow [this document](ftp://ftp.ingenic.cn/3sw/01linux/08doc/mips_toolchain_guide.pdf) to build the toolchain.

Tips: If you use ubuntu to build the toolchain, please change the default shell program to bash to build the toolchain.
```
sudo dpkg-reconfigure dash
```

See [DashAsBinSh](https://wiki.ubuntu.com/DashAsBinSh) for more information.

## u-boot ##

  * [u-boot-1.1.6.tar.bz2](ftp://ftp.ingenic.cn/3sw/01linux/01loader/u-boot/u-boot-1.1.6.tar.bz2)

  * [u-boot-1.1.6-jz-20090216.patch.gz](ftp://ftp.ingenic.cn/3sw/01linux/01loader/u-boot/u-boot-1.1.6-jz-20090216.patch.gz)

  * [uboot\_developer\_guide.pdf](ftp://ftp.ingenic.cn/3sw/01linux/08doc/uboot_developer_guide.pdf)

## linux ##

  * [linux-2.6.24.3.tar.bz2](ftp://ftp.ingenic.cn/3sw/01linux/02kernel/linux-2.6.24/linux-2.6.24.3.tar.bz2)

  * [linux-2.6.24.3-jz-20090218.patch.gz](ftp://ftp.ingenic.cn/3sw/01linux/02kernel/linux-2.6.24/linux-2.6.24.3-jz-20090218.patch.gz)

  * [linux2.6\_developer\_guide\_v1.4.1.pdf](ftp://ftp.ingenic.cn/3sw/01linux/08doc/linux2.6_developer_guide_v1.4.1.pdf)

## rootfs ##

  * [root-jz-20090216.tar.bz2](ftp://ftp.ingenic.cn/3sw/01linux/03root/root-jz-20090216.tar.bz2)

# demo boards #


&lt;hr&gt;


## pavo ##
N/A
# qemu-jz #


&lt;hr&gt;


http://repo.or.cz/w/qemu/qemu-JZ.git

[how to use qemu-jz](qemujz.md)

# jz-hacking #


&lt;hr&gt;


Jz-hacking is a project to hack jz soc based devices, for example mp4/pmp. Currently, the main effort is on porting u-boot/linux to onda vx747.

## source code ##
### jz\_tools ###
http://repo.or.cz/w/jz_tools.git

Some tools used for jz\_hacking.

### jz\_xloader ###
http://repo.or.cz/w/jz_xloader.git

JZ\_xloader is a program to do low level init, pll/sdram for example. It can be uploaded to JZ4740's sram using usb boot. After jz\_xloader initializing SDRAM, the bootloader, u-boot for example, can be loaded into SDRAM.

### jz\_uboot ###
http://repo.or.cz/w/jz_uboot.git

JZ\_uboot is the bootloader for jz4740 based devices. It is based on the source code released by ingenic.

### jz\_linux\_2.6.24.3 ###
http://repo.or.cz/w/jz_linux_2.6.24.3.git

JZ\_linux\_2.6.24.3 is the linux kernel source code for jz4740 based devices. It is based on the source code released by ingenic.

## onda vx747 ##

### uart pins ###

The UART connections on the VX747 board has been found by [panjet](http://www.linuxforum.net/forum/showprofile.php?User=panjet&What=ubbthreads). [Form thread link](http://www.linuxforum.net/forum/showflat.php?Cat=&Board=embedded&Number=707757&page=0&view=collapsed&sb=5&o=0&fpart=4&vc=1)

[uart pins for vx747](vx747uart.md).

### rockbox ###

It is supported by [rockbox](http://www.rockbox.org/twiki/bin/view/Main/OndaVX747) though not fully complete. [This article](http://vm-kernel.org/blog/2009/01/12/how-to-run-rockbox-on-vx747/) describes how to use rockbox on vx747.

### u-boot on vx747 ###
Current Status:
  * u-boot can be run on vx747 now and LCD is working.
  * SD card is working
  * nand flash driver is working
  * programing u-boot into nand flash automatically
  * loading linux kernel from sd card is working

[screenshot:u-boot on onda vx747](http://picasaweb.google.com/lh/photo/K7y9F0VyKRKcTPMEpABhxw?feat=directlink)

### linux on vx747 ###
Current Status:
  * LCD and frame buffer is working (frame buffer console is not working)
  * SD card is working
  * can run rootfs 2.6 (qtopia 1.6.1) released by ingenic

TODO:
  * Sound and mplayer
  * nand flash
  * volume up and down button


[how to run linux on onda vx747](http://vm-kernel.org/blog/2009/02/24/linux-on-onda-vx747/)

[screenshot1](http://picasaweb.google.com/lh/photo/Xv_vJhWVqL4MW8M2YJc0Yw?feat=directlink)
[screenshot2](http://picasaweb.google.com/lh/photo/cV4OYKzAb60m3h40Xamv0A?feat=directlink)
[screenshot3](http://picasaweb.google.com/lh/photo/VMXGs4MUmfyFmOF0ih3lEA?feat=directlink)

<a href='http://www.youtube.com/watch?feature=player_embedded&v=jbMxSP7_jqY' target='_blank'><img src='http://img.youtube.com/vi/jbMxSP7_jqY/0.jpg' width='425' height=344 /></a>

### OEM products ###
  * [Pasen Itouch LE](http://en.pasen.it/product_detail.php?id=36)

# Links #


&lt;hr&gt;


  * [rockbox wiki page](http://www.rockbox.org/wiki/IngenicJz47xx)
  * [forum thread of vx747 hacking(Chinese)](http://www.linuxforum.net/forum/showflat.php?Cat=&Board=embedded&Number=707757&page=0&view=collapsed&sb=5&o=0&fpart=)
  * [Little Linux Laptop: New site dedicated to the cheapest of notebooks](http://www.liliputing.com/2008/08/little-linux-laptop-new-site-dedicated-to-the-cheapest-of-notebooks.html)
  * [a google group about hacking jz4740(in Chinese)](http://groups.google.com/group/jz4740_linux)
  * [alpha 400 UMPC China design company(in Chinese)](http://www.skytone.net.cn/products.php?bigclass=2&smallclass=1&show_type=1)