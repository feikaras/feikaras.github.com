---
layout: post
title: "Ubuntu 12.04下设置ecshop URL Rewrite"
description: ""
category: 
tags: []
---
{% include JB/setup %}
首先，开启apache2的URL rewrite模块
	sudo ln -s /etc/apache2/mods-available/rewrite.load /etc/apache2/mods-enabled/rewrite.load
然后编辑
	/etc/apache2/sites-enabled/000-default
把里面的
	<Directory />和 <Directory /var/www/>的
	AllowOverride None改为AllowOverride all
保存
然后打开ecshop的目录
	把htaccess.txt改名为.htaccess
用
	sudo service apache2 restart
重启apache服务器
去echop后台商店设置里面开启URL重写。
done
