---
layout: post
title:  chsh用法
date:   2016-12-08 18:18:18 +0800
category: 技术
tags:   shell
keywords: shell chsh
description: 
---
# 查看本机中安装了哪些shell   
两种方法可以查看：      

> chsh -l    
> cat /etc/shells    

# 查看当前使用的shell    
两种方法可以查看：     

> echo $SHELL   
> env |grep SHELL    

# 修改使用的shell   
两种方法可以修改：（修改后重启生效）          

> vim /etc/passwd    
> chsh -s    

# 参考   
[1] [linux chsh命令参数及用法详解](http://www.jb51.net/LINUXjishu/57945.html)    

