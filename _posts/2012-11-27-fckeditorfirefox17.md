---
layout: post
title: "FCKEditor不兼容firefox17的解决办法"
description: ""
category: 
tags: []
---
{% include JB/setup %}
所有fck的区域显示为textarea，其实是firefox更换UA导致的
解决办法参见stackoverflow或者https://bugzilla.mozilla.org/show_bug.cgi?id=814019

备注:
Firefox 17的UA:
    Mozilla/5.0 (X11; Linux i686; rv:17.0) Gecko/17.0 Firefox/17.0
Firefox 16的UA:
    Mozilla/5.0 (X11; Linux i686; rv:16.0) Gecko/20100101 Firefox/16.0

从Gecko后面的数字可以明显看出问题，fck通过判断gecko后面的数字来得知浏览器是否兼容的。
