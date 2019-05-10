---
title: "超低温探头ATM部件维修/Cryoprobe ATM Unit Main Repairing on Bruker Avance III HD 850MHz"
date: 2019-05-10T10:52:20+08:00
lastmod: 2019-05-10T10:52:20+08:00
draft: false
keywords: ["ATM", "Cryoprobe", "850MHz"]
description: "超低温探头的ATM部件维修"
tags: ["NMR"]
categories: ["核磁技术"]
author: "冯柳宾"
---

今年3月份的时候，850MHz的超低温探头CPTCI的ATM出现调谐跳不过去的问题，底下是我的维修记录。曾经咨询过厂商，厂商的意思是如果给我更换一个好的ATM部件，可以用，就说明是ATM的问题，此部件报价13万人民币。太贵，承受不起，我就自己修了。

<!--more-->

### 问题描述：
15N调谐卡住，拔插PCIS线以后导致ATMA初始化都不行，报错
```
Atma info
Error: canot create probe-obj Probe-MotorBase init: doInitMove Motor-Nr: 7<15N Tune>: canot move to position -12 (current 0)
```
![error-picture](/images/error-1.jpg)
```
Error： canot create probe-obj Probe-MotorBase init: doInitMove: Motor: initMove drive get stuck in the limitposition: Motor-Nr: 7<15N Tune>
```
![error-picture2](/images/error-2.jpg)

### 可能的问题

1. 最大可能是ATM部件出现问题。因为报错显示是15N的Tune通道卡住。

	1.1 如果是ATM部件出问题，最有可能是Tune的马达坏了。因为850MHz磁体底部的磁场很大，可能马达会被磁化掉。

	1.2 另外就是其他部件出了问题，比如ATM部件上面有一个轴心铜棒子可能会歪了，导致上下伸缩出现问题。

2. 最坏情况就是探头里面的调谐杆出现问题。这个就比较麻烦了。

### 尝试解决方案

1. 删除ATMA原本配置文件。参考Bruker提供的manual。重启topspin，拔插PCIS；失败！

2. 拆下探头底部的ATM部件（在拆之前请先在cryopenel里面把bottom temp关闭），
用手动调谐杆调8个调谐通道，发现所有的通道是可以无阻碍的调到底部和回来的。此处说明探头的调谐杆没有问题，问题不是出在探头的调谐杆里面。此时如果不用自动ATM部件，可以用手动调谐做实验。此时我们按压ATM部件7Tune通道，发现那个金铜色的杆子按压有一定的阻力。尝试按压几次，然后装回探头，曾经有一次ATMA可以通过，但是在调谐15N的时候Tune还是有问题，很快就到底部了。所以怀疑可能7<15N Tune>的调谐马达可能有问题。

![atm-upper](/images/atm-upper.jpg)

3. 拆开探头发现这个ATM部件里面的调谐马达是瑞士一家公司Maxon生成的无刷马达，编号为134851。在瑞士这家公司的官网也这个编号的马达提供。我从武汉一家公司采购到这个马达。

![maxon-motor](/images/atm-motor.jpg)

4. 由于之前并不懂得如何拆这个ATM部件，很多都是摸索前进的。所以我并不清楚这个部件是如何工作的，也觉得有可能是里面有什么地方卡住导致调谐问题。在尝试多次以后，终于了解并成功拆开ATM部件的，发现在7<15N Tune>这个调谐杆附件有一个电线会蹭到调谐杆的一个指示凹起，目前那个电线表皮已经有一部分被蹭破。所以我怀疑这这个电线导致7通道调谐卡住。底下有配图。目前我把这个电线拉远离这个调谐杆，重新装回去探头，ATMA可以顺利通过。同时手动ATMM调谐15N通道也可以漂亮完成，所以我认为就是这个原因导致的。

5. 这次问题的解决关键是拆开这个ATM部件，由于厂商不愿意告知我们这个部件的拆卸过程（厂商直接更换此部件，报价超过13万人民币），在摸索过程中会有一些风险。底下我详尽讲解一些这个ATM单元的拆装过程。

### ATM单元拆装过程

**注意： 在Bruker的 ATM Accessory User Manual中提到安装ATM部件时候，记得把bottom heater关掉，不然可能会引起冷头回温**
```
Enter the service mode in CryoTool or CryoPanel and switch off the Temp. Ctl 3
(Bottom-H).
After this, you can detach the bottom heater cable from the mechanical tuning &
matching adapter.
When the ATM Accessory is mounted and bottom heater cable is connected, do
not forget to switch on the Temp. Ctl 3 (Bottom-H) in CryoTool or CryoPanel.
```
小心拆下探头底下的ATM单元，下面我详细说明如何拆解ATM单元，可以用于更换马达或者寻找其他故障原因。

1. 拆开两个内六角螺丝，四个一字螺丝，如下图：

![screw](/images/atm-screw.png)

2. 接着从顶部往下推，这个内部结构就会从外壳推开。

![atm-unmout](/images/atm-unmount.jpg)

3. 这次故障主要是由于在7<15N Tune>这个调谐杆附件有一个电线会蹭到调谐杆的一个指示凹起，目前那个电线表皮已经有一部分被蹭破。如下图：

![atm-problem](/images/atm-problem.jpg)

