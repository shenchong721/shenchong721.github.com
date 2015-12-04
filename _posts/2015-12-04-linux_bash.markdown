---
layout: post
title: "linux实用命令"
date: 2015-12-04 16:54
category: "备忘"
tags: [linux, bash]
---
{% include JB/setup %}

参考博客：[JohnTsai](http://www.cnblogs.com/JohnTsai/p/4027229.html)

---

在linux的使用中经常会需要用到一些少用但实用的命令，在此做一记录，方便查询。

*[**1.sed**](#1)  
*[2.gawk](#2)
* [1.sed](#4)  
* [2.gawk](#5)

<h1 id="1">1.sed</h1>

	$echo "this is a test " sed `s/a/a sed/`  #该命令将‘a’换成‘a sed’;
	$sed -e `s/a/b/ ; s/c/d/` txt #执行多个命令时加上参数-e;且命令之间用分号隔开

<h2 id='2'>2.gawk</h2>
你好２


####注：
DISPLAY=IPB:0.0 为ip加上端口号，[ipA]:[portA].[portB]
其中：portA为display number，portB为screen number，通常为０
