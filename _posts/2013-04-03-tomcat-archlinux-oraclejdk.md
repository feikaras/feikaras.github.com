---
layout: post
title: "ArchLinux下使用oracle jdk安装tomcat的问题"
description: ""
category: 
tags: []
---
{% include JB/setup %}
	sudo systemctl enable tomcat7
	sudo systemctl start tomcat7
tomcat用pacman安装完毕后启动失败
提示servelet启动失败
去/etc/systemd/system/multi-user.target.wants打开tomcat7.service
重新编辑JAVA_HOME路径后
	sudo systemctl daemon-reload
	suso systemctl restart tomcat7
搞定,如果不daemon-reload貌似不会立刻重读配置文件

