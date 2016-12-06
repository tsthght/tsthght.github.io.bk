---
layout: post
title:  如何制作RPM包
date:   2016-12-06 14:28:49 +0800
category: 技术
tags:     rpmbuild
keywords: rpmbuild, RPM
description: 
---
# 简介   
RPM也是一个递归缩写（RPM Package Manager），类似众所周知的还有：PNG（PNG's not GIF）、GNU（GNU's not Unix）。之前是RedHat的软件包管理，开源后被移植到SunOS/Solaris/AIX/Irix等UNIX-LIKE系统之上，其遵循GPL协议。   
RPM包中除了程序运行时所需的文件，也包括其他文件：保证其正常的附加文件和特定版本文件（软件包依赖关系），其可以使用户以binary形式安装软件包，并且替用户检查相关的库文件。      

# 类型    
二进制类包：包括RPM安装包和调试信息包    
源码类包：源码包和开发包     

# 制作过程    
- 创建目录结构    
> yum install rpmdevtools      
> rpmdev -setuptree          

上述命令会在当前用户主目录下创建RPM构建的根目录结构, 如果需要改变默认位置，可以修改配置文件: ~/.rpmmacros 中的变量_topdir。目录结构如下:                 
> .     
> |__BUILD(打包过程的工作目录)    
> |__RPMS(存放生成的二进制包，不同硬件平台存放在不同的文件夹下)    
> |__SOURCES(存放打包资源，包括源码打包文件和补丁文件)     
> |__SPECS(存放SPECS文档)    
> |__SRPMS(存放生成的源码包)     

- 撰写SPECS文档      
- 放置源代码    
- 构建RPM包     
> cd ~/rpmbuild    
> rpmbuild -ba SPECS/xxx.spec     

# 错误与解决办法         
1. error: Installed(but unpackaged)files(s) found     
找到/usr/lib/rpm/macros中     
%__check_files     /usr/lib/rpm/check-files %{buildroot}   注释掉    

# 参考     
[1] [有趣的递归缩写](http://www.cnblogs.com/wonderow/archive/2005/07/09/189523.html)     
[2] [制作RPM包](https://segmentfault.com/a/1190000002539129)     
[3] [中间遇到了 error: Installed (but unpackaged) file(s) found: 解决的办法是](http://blog.sina.com.cn/s/blog_467eb8ca010008p3.html)     
[4] [制作rpm包： error: Installed (but unpackaged) file(s) found](http://blog.sina.com.cn/s/blog_467eb8ca010008p0.html)     


