---
layout: post
title: "php5.3+apache2.4 windows安装攻略"
description: "在windows下安装php的配置旅程"
category: 
tags: [php]
---
{% include JB/setup %}
apache2.4用  [这里](http://www.apachelounge.com/download/)  下的VC10版本*并非apache.org上的vc6版本*

php5.3用   [这里](http://windows.php.net/download/)   下的*VC9 x86 Thread Safe*的*Installer*版

apache按照自带的说明，把里面的apache24目录解压到c:\
cmd下进C:\Apache24\bin\运行httpd.exe -k install
服务里面去启动apache

php安装的时候选择apache cgi模式。安装到c:\php

打开C:\Apache24\conf\httpd.conf修改文件末尾的

	#BEGIN PHP INSTALLER EDITS - REMOVE ONLY ON UNINSTALL
	ScriptAlias /PHP/ "c:/PHP/"
	AddType application/x-httpd-php .php
	Action application/x-httpd-php "c:/PHP/php-cgi.exe"
	#END PHP INSTALLER EDITS - REMOVE ONLY ON UNINSTALL

如上并且，查找`<Directory`
找到`<Directory "c:/Apache24/cgi-bin">`字样（或者cgi-bin那行）
改为`<Directory "c:/PHP">`
保存重启apache服务


关于Zend Guard Loader

Windows 下面的 Zend Guard Loader 不支持php5.3 VC9 x86 Thread Safe而，php5.3  VC9 x86 Non Thread Safe 又不支持 apache。所以安装的话，就需要安装在iis或者和nginx搭配。


备注：当前版本,php5.3.17,apache2.4.3

参考文档：

* [Troubleshooting PHP 5.3.3 installation](http://www.websiteadministrator.com.au/articles/install_guides/installing_php533_pg7.html)
* [Testing PHP 5.3.3 Installation Configuration](http://www.websiteadministrator.com.au/articles/install_guides/installing_php533_pg6.html)
* [Windows下的PHP 5.3.x安装 Zend Guard Loader 方法](http://hi.baidu.com/iamcyh/item/0c8455dc12c38f10e0f46f8d)
