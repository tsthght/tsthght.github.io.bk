---
layout: post
title:  pkg-config用法
date:   2016-12-09 15:35:49 +0800
category: 技术
tags:     pkg-config
keywords: pkg-config
description: 
---
# 简介    
pkg-config 当你从源代码编译软件时，用来提供依赖库的信息的软件    
它输出的已安装的库的版本信息包括：     
1) C/C++编译器需要的参数   
2) 连接器需要的参数    
3) 已安装软件包的版本信息   

# 用法   

- 命令行中
```
pkg-config --libs --cflags XXX
```

- 编译连接时   
```
gcc XXX.cpp \`pkg-config --libs --cflags XXX\` 
```

- make中    
```
INCLUDE=$(shell pkg-config --cflags XXX)
LIBS=$(shell pkg-config --libs XXX)
```

# 工作原理     
pkg-config命令通过检索存放于系统的\*.pc文件来给出相应的库的输出。    
例如opencv.pc中的内容     

```
\# Package Information for pkg-config

prefix=/usr
exec_prefix=${prefix}
libdir=${exec_prefix}/lib
includedir_old=${prefix}/include/opencv
includedir_new=${prefix}/include

Name: OpenCV
Description: Open Source Computer Vision Library
Version: 2.3.1
Libs: -L${libdir} -lopencv_core -lopencv_imgproc -lopencv_highgui -lopencv_ml -lopencv_video -lopencv_features2d -lopencv_calib3d -lopencv_objdetect -lopencv_contrib -lopencv_legacy -lopencv_flann
Cflags: -I${includedir_old} -I${includedir_new}

```

这个文件来源于那里呢？这个\*.pc文件在你的库安装包里，一般是库的打包者或发行者设置好的。当安装库时，\*.pc文件被放于你系统重的某一个文件夹中（根据你的系统设置，一般存放的位置有/usr/lib/pkgconfig/等）

# 参考   
[1] [pkg-config命令了解和使用](http://oucmsc.blog.163.com/blog/static/126340328201321362916529/)    

