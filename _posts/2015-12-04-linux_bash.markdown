---
layout: post
title: "linux实用命令"
date: 2015-12-04 16:54
category: "备忘"
tags: [linux, bash]
---
{% include JB/setup %}


在linux的使用中经常会需要用到一些少用但实用的命令，在此做一记录，方便查询。

* [**1.sed**](#1)  
* [**2.gawk**](#2)

<h1 id="1">1.sed</h1>

* 模式s/pattern/replacement/flags:

    + 数字: 表示新文本将替换第几处模式匹配的地方
    + g: 表明新文本将会替换所有已有文本出现的地方
    + p: 表明原来行的结果要打印出来
    + w file: 表明将替换的结果写到文件中去

具体代码如下：
	
	$echo "this is a  test" sed `s/test/mytest/`  #该命令将‘test’换成‘mytest’;
	$echo "this is second test of sed test" sed `s/test/mytest/2`  #参数2表示是替换第二个test，默认是替换第一个;
	$sed -e `s/a/b/ ; s/c/d/` txt #执行多个命令时加上参数-e;且命令之间用分号隔开

<h2 id='2'>2.gawk</h2>
+ gawk脚本命令必须放到两个大括号内，且放到单引号中;
+ gawk会默认用空格符给输入字符串划分;  

具体命令如下：
	
	$gawk '{print $1}' txt  #将txt中每行数据的第一个划分打印出来    
	$gawk -F: '{print $1}' /etc/passwd  #换用其他的换行符，可以加-F选项
	$gawk 'BEGIN{print "hello!"} {print $1}' txt #BEGIN表示最gawk在读取数据前执行的命令
	$gawk 'BEGIN{print "begin"} {print $1} END{print "end"}' #END表示gawk会在读取完数据之后执行



