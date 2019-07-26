---
title: "Win7 system restore at PC with Topspin3.2pl2 of Bruker Avance III HD 600 MHz"
date: 2019-07-26T10:34:55+08:00
lastmod: 2019-07-26T10:34:55+08:00
draft: false
keywords: ["Topspin", "600MHz"]
description: "Bruker核磁谱仪采集电脑系统恢复"
tags: ["NMR"]
categories: ["核磁技术"]
author: "冯柳宾"
---

2019年7月20日，600 MHz谱仪采集计算机卡顿，重启启动不起来，检查硬盘发现硬盘坏道比较多。

<!--more-->

####  问题描述（Question）

采集计算机（HP Z420）由于长时间运行（5年半），平时几乎不关机，导致磁盘会有一些坏道和损坏。在7月20号发现电脑运行特别卡顿，尝试重启，开机启动不起来。经Win PE开机检测磁盘系统盘有比较多的坏道，此硬盘已经不能使用，需要重新更换硬盘，并且重装系统和Topspin。

#### 配件更换（Hardware Change）

原配硬盘：WD Blue 1.0 TB 64 MB Cache 7200

更换硬盘：WD Glod 1.0 TB 128 MB Cache 7200 企业级

> 注： 原来系统硬盘如果是1.0 TB，由于是系统备份恢复，更换的硬盘容量不能小于1.0 TB。由于是长时间开机，可以更换好一点的硬盘（企业级别）。

#### 更换和系统重装过程（Os system restored）

要求：系统有备份（DVD，U盘，一般Bruker电脑主机里面会有一个出厂的时候系统备份U盘）；其次Topspin要有备份nmrsave，这个是用来恢复软件Topspin的仪器配置参数（机柜，探头等等参数）。

> 最好平时有nmrsave的习惯，同时因为nmrsave是不备份Topspin license和accept实验的，需要自己手动备份

Bruker提供的放在电脑主机里面的系统恢复U盘如下，这里面是Acronis True Image的系统备份盘。：![](/images/os_restore_usb.jpg)

更换好电脑硬盘，把这个U盘插入电脑USB接口，因为bruker提供的电脑默认设置USB启动为优先。所以电脑就会马上进入这个恢复U盘，这个恢复过程会擦除这个硬盘上所有数据，重新分区，写入原本的系统，并且会安装上Topspin。刚开始检测如果发现硬盘小于之前备份时候硬盘大小，告诉你没有办法恢复。如果没有其他错误，它会提示说擦除原有所有数据，接下去整个过程自动完成，差不多20分钟恢复完成系统关闭。接来下，你拔掉U盘，重启电脑，刚开始系统会进行基本配置，中间可能会有重启过程。

这些都完成后，系统会弹出一个幻灯片，告诉你接下来设置参数，其中账号（nmr，nmrsu和root）建立，两个网卡设置，都是自动完成，然后系统关闭这个幻灯片，登入root账号，可以更新Windows系统（Windows Update），安装Acrobat Reader，AntiVirus。由于刚安装完成后，系统只有一个系统分区，您可以自己缩小分区，新建其他分区。（Control Panel，System and Security, Adminstrative Tools, Create and format hard disk partitions)。

然后重启PC，等电脑重启以后，重启机柜里面所有模块，打开Topspin，这个时候会弹出让你cf。这个时候你可以先不要cf，先把nmrsave的备份文件restore以后再做cf，这个时候原则上仪器所有配置都配好了。如果没有什么问题，这样子就可以正常做实验了。

#### 其他问题（others）

假如您要安装更新版本的Topspin，首先要考虑这个版本的Topspin是否满足您机柜；就算您的机柜可以满足，可能安装完以后，cf的时候会弹出说一些硬件对应的firmware需要更新。

