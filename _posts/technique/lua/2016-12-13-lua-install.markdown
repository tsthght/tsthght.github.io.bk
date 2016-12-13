---
layout: post
title:  centos 安装lua 
date:   2016-12-13 16:22:24 +0800
category: 技术
tags:   lua
keywords: lua
description: 
---
1. 下载安装包   
> wget http://www.lua.org/ftp/lua-5.3.1.tar.gz    

2. 解压   
> tar zxf lua-5.3.1.tar.gz   

3. make && make install   
> cd lua-5.3.1   
> make linux test   
> make linux 
> make linux install    

4. 报错   
如果在make linux test过程中报错如下：

```
make[2]: *** [lua.o] 错误 1
make[2]: Leaving directory `/home/jackluo/Downloads/lua-5.2.2/src'
make[1]: *** [linux] 错误 2
make[1]: Leaving directory `/home/jackluo/Downloads/lua-5.2.2/src'
make: *** [linux] 错误 2
```
> yum install libtermcap-devel ncurses-devel libevent-devel readline-devel    
> make linux  
> make linux install   


