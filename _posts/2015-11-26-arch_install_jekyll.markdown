---
layout: post
title: "archlinux 安装 jekyll"
date: 2015-11-26 20:34
category: "archlinux"
tags: [archlinux]
---
{% include JB/setup %}

参照博客:[http://litchiware.github.io](http://litchiware.github.io/archlinux/2015/08/23/archlinux%E4%B8%8B%E5%AE%89%E8%A3%85jekyll/
)
- - - 

## 安装jekyll
Jekyll是一个静态网站生成工具。它允许用户使用HTML、Markdown或Textile来建立静态页面，然后通过模板引擎Liquid（[Liquid Templating Engine](http://liquidmarkup.org)）来运行。  
使用如下命令安装jekyll

	$ gem update
	$ gem install jekyll

在执行 `gem update` 时提示如下错误：

    Error fetching https://rubygems.org/:
            Errno::ECONNRESET: Connection reset by peer - SSL_connect (https://api.rubygems.org/specs.4.8.gz)

原因是 https://rubygems.org/ 源被GFW墙掉了，需要重新设置源

	$ gem sources #显示当前源
	$ gem sources -r https://rubygems.org/ #删除当前源
	$ gem sources -a https://rubygems.org/ #添加新的源 

修改源之后就可以用之前的命令安装jekyll了

