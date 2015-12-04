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

###*[1.sed](#1)  
###*[2.gawk](#2)
* [1.sed](#1)  
* [2.gawk](#2)
<h1 id="1"1.sed></h1>
你好

<h2 id='2'2.gawk></h2>
你好２


分别执行一下命令:    

	在A上执行: $ export DISPLAY=IPB:0.0 #指定Ａ的显示位置为B
	在B上执行: $ xhost+IPA  #将Ａ加入到xhost中去
	之后，在Ｂ上执行：$ ssh -x IPA　＃用ssh连接Ａ，此时便可以在Ｂ上显示Ａ的图形界面了。

####注：
DISPLAY=IPB:0.0 为ip加上端口号，[ipA]:[portA].[portB]
其中：portA为display number，portB为screen number，通常为０
