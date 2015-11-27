---
layout: post
title: "linux远程显示桌面"
date: 2015-11-27 17:48
category: "备忘"
tags: [linux]
---
{% include JB/setup %}

- 服务器A：无图形界面，IPA
- 客户机B：有图形界面，IPB
- 现在需要将A的图形界面显示在B上   
分别：

    Error fetching https://rubygems.org/:
            Errno::ECONNRESET: Connection reset by peer - SSL_connect (https://api.rubygems.org/specs.4.8.gz)

原因是 https://rubygems.org/ 源被GFW墙掉了，需要重新设置源 
分别执行一下命令:    

	在上执行: $ export DISPLAY=IPB:0.0 #指定Ａ的显示位置为B
	在B上执行: $ xhost+IPA  #将Ａ加入到xhost中去
	之后，在Ｂ上执行：$ ssh -x IPA　＃用ssh连接Ａ，此时便可以在Ｂ上显示Ａ的图形界面了。

####注：
DISPLAY=IPB:0.0 为ip加上端口号，[ipA]:[portA].[portB]
其中：portA为display number，portB为screen number，通常为０
