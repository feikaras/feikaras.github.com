---
layout: post
title: "Slackware 64 下 wine 32bit应用程序(32bit 普通Linux程序)的OPENGL加速问题"
description: ""
category: 
tags: []
---
{% include JB/setup %}
解决方法：
	 LIBGL_DRIVERS_PATH=/usr/lib/xorg/modules/dri wine something.exe
来启动程序
一劳永逸就写入/etc/profile
	export LIBGL_DRIVERS_PATH="/usr/lib64/xorg/modules/dri:/usr/lib/xorg/modules/dri"
