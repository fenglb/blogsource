---
title: "Bruker pulse program two character code definitions"
date: 2019-06-17T22:39:05+08:00
lastmod: 2019-06-17T22:39:05+08:00
draft: false
keywords: ["pulse program", "bruker"]
description: ""
tags: []
categories: [核磁技术]
author: "冯柳宾"
---
以下内容拷贝至[这个文档](http://web.mit.edu/speclab/www/Facility/TIPS/Bruker_2_ch_defs.pdf)

For Bruker pulse programs the first characters (usually 4, but at a maximum 6) specify the type of
experiment, e.g. DEPT, COSY, NOESY etc.. Further properties of the pulse program are indicated by a
two-character code, which is added to the name in alphabetical order. For 2-D experiments the default
version is "absolute value" and "without dummy scans". H- or X-decoupling is assumed to be default for
heteronuclear experiments, but not for homonuclear ones (with the exception of inad).
In case of redundant information some two-character codes may be omitted.

<!--more-->

The two-character codes used are the following:

bi with bird pulse for homonuclear J-decoupling

bp bipolar gradients

cp with composite pulse

ct constant time

cw decoupling using cw command

dc decoupling using cpd command

df double quantum filter

di with DIPSI mixing sequence

dh homonuclear decoupling in indirect dimension

dw decoupling using cpd command only during wet sequence

dq double quantum coherence

ea phase sensitive using Echo/Anti-echo method

ed with multiplicity editing

et phase sensitive using Echo/Anti-echo-TPPI method

fb using f2 - and f3 - channel

fd using f1 - and f3 - channel (for presaturation)

fr with presaturation using a frequency list

ft using f1 -, f2 - and f3 - channel (for presaturation)

fh F-19 observe with H-1 decoupling

fp a flip-back pulse

fl for F-19 decoupler

f2 using f2 - channel (for presaturation)

f3 using f3 - instead of f2 - channel

f4 using f4 - instead of f2 - channel

gd gated decoupling using cpd command

ge gradient echo experiment

gp coherence selection using gradients with ":gp" synthax

gr coherence selection using gradients

gs coherence selection using shaped gradients

hc homodecoupling of a region using a cpd-sequence

hd homodecoupling

hf H-1 observe with F-19 decoupling

hs with homospoil pulse

ig inverse gated

ii using inverse (invi/HSQC) sequence

im with incremented mixing time

i4 inverse (inv4/HMQC) sequence

jd homonuclear J-decoupled

jr with jump-return pulse

lp with low-pass J-filter

lq with Q-switching (low Q)

lr for long-range couplings

mf multiple quantum filter

ml with MLEV mixing sequence

nd no decoupling

no with NOESY mixing sequence

pc with presaturation and composite pulse

pg power-gated

pl preparing a frequency list

pn with presaturation using a 1-D NOESY sequence

pr with presaturation

ps with presaturation using a shaped pulse

qn for QNP-operation

qs phase sensitive using qseq-mode

rd refocused

rl with relay transfer

rs with radiation damping suppression using gradients

ru using radiation damping compensation unit

rv with random variation

r2 with 2 step relay transfer

r3 with 3 step relay transfer

se spin echo experiment

sh phase sensitive using States et al. method

si sensitivity improved

sm simultaneous evolution of X and Y chemical shift

sp a shaped pulse

st phase sensitive using States-TPPI method

sy symmetric sequence

tf triple quantum filter

tp phase sensitive using TPPI

tr using TROSY sequence

ul using a frequency list

us updating shapes

wg watergate using a soft-hard-soft sequence

w5 watergate using W5 pulse

xf x-filter experiments

x1 x-filter in F1

x2 x-filter in F2

zf with z-filter

zq zero quantum coherence

1d 1-D version

1s using 1 spoil gradients

11 using 1-1 pulse

19 using 3-9-19 pulse

2h using 2H lockswitch unit

2s using 2 spoil gradients

3d 3-D sequence

3s using 3 spoil gradients

30 using a 30 degree flip angle

45 using a 45 degree flip angle

90 using a 90 degree flip angle

135 using a 135 degree flip angle

A phase-sensitive (TPPI) NOESY experiment with presaturation would then be: noesy + pr + tp = noesyprtp.
