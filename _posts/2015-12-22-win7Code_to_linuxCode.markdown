---
layout: post
title: "win7到linux下文件乱码问题"
date: 2015-12-22 11:31
category: "备忘"
tags: [linux]
---
{% include JB/setup %}

---

参考文献１：[红黑联盟](http://www.2cto.com/os/201211/167958.html)

---

linux下经常遇到的编码问题。如果你需要在Linux中操作windows下的文件，那么你可能会经常遇到文件编码转换的问题。Windows中默认的文件格式是GBK（gb2312），而Linux一般都是UTF-8。

* [**1.查看文件编码**](#1)  
* [**2.文件内容转换**](#2)
* [**3.文件名转换**](#3)


<h1 id="1">1.查看文件编码</h1>

+ 方法一：file filename
+ 方法二：在vim中可以直接查看文件编码：     
　　:set fileencoding



<h1 id="2">2.文件内容转换</h1>
+ 方法一：直接在vim中转换文件编码：  
在Vim中直接进行转换文件编码，比如将一个文件转换成utf-8格式  
　　:set fileencoding=utf-8
+ 方法二：在vim中设置文件集合：  
 即要对哪些文件进行操作，可以使用通配符，比如我通常是对 C/C++ 源程序进行编码转换  
　　:args *.h *.cpp  
给出要在每个文件上执行的命令，这里是转换编码：  
　　:argdo set fenc=utf-8 | update    
+ 方法三:iconv转换   
　　iconv -f GBK -t UTF-8 file1 -o file2   
这里便是将一个UTF-8 编码的文件转换成GBK编码   




<h1 id="３">３.文件名转换</h1>

convmv就是更改文件名编码方式的一个工具：   
　　:sudo convmv -f gbk -t utf-8 -r –notest  /home   
就是将/home目录下原来文件名是gbk编码方式的全部改为utf-8格式的。这里 -f  后面为原来的编码方式，-t 后面是要更改为的编码方式， -r 表示这个目录下面的所有文件， –notest 表示马上执行，而不是仅仅测试而已。另外这命令好像要root才能执行，因此要加上 sudo。
