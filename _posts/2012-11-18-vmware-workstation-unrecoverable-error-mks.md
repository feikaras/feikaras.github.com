---
layout: post
title: "Vmware Workstation unrecoverable error: (mks)"
description: ""
category: 
tags: []
---
{% include JB/setup %}
无论是重装，新建虚拟机，都会发生Vmware Workstation unrecoverable error: (mks)的时候。。
我找了下google发现这个问题提法很多。感觉和amd驱动有关。
我突然想起刚刚更新了ati catalyst 12.11beta到beta8。
一测，果然发现开了3d加速就挂了。
具体设置下固定了虚拟机桌面和分辨率尺寸。问题解决了。

