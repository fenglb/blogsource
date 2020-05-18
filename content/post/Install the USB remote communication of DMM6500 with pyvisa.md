---
title: "Install the USB remote communication of DMM6500 with pyvisa"
date: 2020-03-16T22:39:05+08:00
lastmod: 2020-03-16T22:39:05+08:00
draft: false
keywords: ["python", "DMM6500"]
description: ""
tags: []
categories: [开发]
author: "冯柳宾"
---
安装DMM6500数字万用表的USB远程控制教程
<!--more-->

1. Install Python 3.2+ and pyvisa. [linker](https://pyvisa.readthedocs.io/en/1.8/getting.html), Because Qt 4.8 and VS2010 are 32-bit development environment, so download the x86 installer of Python 3.8.1, even in the x64 OS.

   ```  pip instal -U pyvisa ```

2. install ni-visa_19.5_online_repack.exe. The NI-VISA library bitness has to match the Python bitness. ``` python -m visa info``` , PyVISA works with 32- and 64- bit Python and can deal with 32- and 64-bit VISA libraries without any extra configuration.
3. Install iviShareComponent_2.6.1, this part sure be 64 bit if your OS is 64 bit;
4. Now you can install the Keithley DMM6500 driver, also install 64 bit if your OS is 64 bit;

When I use the pyvisa in Qt development with Python, I can only use the Python DLL without the Python environment. But with the NI-VISA to communicate between DMM6500 and PC, you must install the ni-visa package and DMM6500 driver.

#### Q&A

Q1. When in the x64 OS and use 32bit development enironment, which bitness of the DMM6500 driver is choose one ( x64 or x86 )?

Q2. Qt and VS2010 use the Python, first error is "inittype.h No such file or directory".

A2. Because the MSVC not has this file "inittype.h", you can download from [google code](https://code.google.com/archive/p/msinttypes/downloads). 

Q3. "include\object.h"(190) error 语法错误：";"

A3.  Just change the "slots" to "_slots", because Qt and Python have conflict.

