---
title: "Archlinux中使用PPTP VPN设置"
date: 2019-06-08T12:05:36+08:00
lastmod: 2019-06-08T12:05:36+08:00
draft: false
keywords: [Archlinux, PPTP]
description: ""
tags: []
categories: [Linux]
author: "冯柳宾"
---

在Archlinux中设置VPN连接, 以下是相应的设置方法. 可以参考[Archlinux使用pptpclient](https://www.jianshu.com/p/80cc6514d3f1).

<!--more-->

## Install pptpclient and configurate

> sudo pacman -S pptpclient
>
> pptpsetup --create tunnel_name --server vpn.example.com --usrname alice --password pd --encrypt

## Connect and disconnect

> sudo pon tunnel_name
>
> sudo ip route add default dev ppp0

> sudo ip route del default dev ppp0
>
> sudo poff tunnel_name

这样子就应该可以连接到VPN服务了.

## Error

When starting PPTP client, the pppd process cannot locate the appropriate module:

> Couldn't open the /dev/ppp device: No such device or address
>
> Please load the ppp_generic kernel module.

The solution is to edit the /etc/modprobe.d/modules.conf file and change. This can reference [archlinux wiki](https://wiki.archlinux.org/index.php/Ppp#pppd_cannot_load_kernel_module_ppp_generic)