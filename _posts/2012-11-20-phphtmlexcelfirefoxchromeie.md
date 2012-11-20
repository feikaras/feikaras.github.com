---
layout: post
title: "PHP生成html格式的excel表格,Firefox和Chrome没问题但是IE挂掉的现象"
description: ""
category: 
tags: []
---
{% include JB/setup %}
如果使用
    window.open('goodsDown.php?a{params}')
打开一个即时生成的php表格的话，IE会产生一个错误
    Internet Explorer 无法下载 goodsDown.php
    Internet Explorer 无法打开该 Internet 站点。请求的站点不可用，或找不到。请以后再试。
如果使用
    windows.location.href='goodsDown.php?a{params}';
正常了。

关于php中文文件名。如果使用mb_convert_encoding函数转换成gbk的话。Linux下Firefox下载会出现文件名乱码。
如果不采用任何转码方式，因为PHP一般采用utf-8存储，IE会乱码，火狐正常。
如果用rawurlencode转码的话，Firefox文件名会变成转码后的情况,而IE是正常的。所以如果对用户代理进行判断则可以解决问题。PHP一般用utf-8编码保存，所以遇到 Firefox可以直接输出，而遇到IE可先进行rawurlencode转码后使用。
例:
    if (preg_match('/MSIE/',$_SERVER['HTTP_USER_AGENT'])) {
        $file_name = rawurlencode($file_name);
        } 
切忌使用urlencode编码。
