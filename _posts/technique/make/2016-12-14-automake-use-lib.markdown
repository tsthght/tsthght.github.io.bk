---
layout: post
title:  automake中使用/创建静态/动态库  
date:   2016-12-14 07:09:49 +0800
category: 技术
tags:     automake
keywords: automake
description: 
---
#  检查第三方库   
```
AC_CHECK_LIB(libname, libfunc, [yes-do], [no-do])
```

# 使用第三方库  
```
AM_CPPFLAGS=-I ...
AM_LDFLAGS=-l....
```

# 创建静态库   


# 参考   
1. [AC_CHECK_LIB工作原理](http://blog.csdn.net/sukhoi27smk/article/details/19418421)   
2. [使用Automake 创建和使用静态库](http://www.cnblogs.com/shenlian/archive/2011/10/21/2220367.html)

