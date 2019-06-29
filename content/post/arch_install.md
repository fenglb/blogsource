---
title: "Install Archlinux"
date: 2019-06-29T16:40:41+08:00
lastmod: 2019-06-29T16:40:41+08:00
draft: false
description: "install archlinux"
tags: [Archlinux]
categories: [Linux]
author: "冯柳宾"
---

Install archlinux
<!--more-->

1. down the archlinux from the netword and make the USB booter through the ubuntu `dd`

2. change the computer bios to boot from the USB

3. choose the first option Archlinux

4. make sure the internat connection. you can use `ping` to check the internat status. 
If you use the ether, you can make sure the dhpdc service is active and start.
And maybe you only use the wireless, you can use `iw` and `wpa_supplicant`

5. you can select the best mirrorlist from /etc/pacman.d/mirrorlist, and delete the 
others. As my test, the aliyun, 163 and utcn are good. At the end, you can text the
`pacman -Syy` to update the list.

6. Now you can do partition. I make /boot, /home, /, and /swap. Because the windows 10
OS has been installed, so there is the efi/boot. This step I use the `fdisk -l` to view
the detail of the partition of system, and use the `cfdisk` to create the new partition.

7. You must format the new partition, use the `mkft.ext4` and `mkswap` and `swapon`.

8. mount the root to /mnt. The home and boot, you must mkdir it and mount them.

9. Install the base and base-devel to the system, it spent more or less 10 minutes.

10. set the system clock and local parameter.

### Install i3-wm at the Arch OS.
