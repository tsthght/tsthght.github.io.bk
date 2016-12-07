---
layout: post
title: Linux程序设计 第9章
date: 2016-12-07 08:36:11 +0800
category: 笔记
tags: notes rpm
keywords: notes rpm
description:
---
## 9.5 发行软件     
### 9.5.1 patch程序  
软件发行后，对软件的漏洞或是功能增强、升级的情况不可避免。对于源代码压缩后可能体积也比较大，但是各个版本之前的差别却非常小，为了减少传输新代码产生的资源消耗，可以使用工具程序——patch。    

> diff file1 file2 > diffs     
> patch file1 diffs   
> patch -R file1 diffs    

### 9.5.2 其他软件发型工具     
Linux的程序和源代码通常以打包压缩文件的格式发行，文件名中包含软件的版本号， 文件后缀名.tar.gz 或 .tgz。    

## 9.6 RPM软件包    
RPM软件包管理程序，最初的名字为RedHat软件包管理程序，随后RPM主键成为了其他Linux发行版所接受的一种软件包格式。     

主要优点：     
- 使用广泛   
- 安装、删除只需要一条指令    
- 只需要处理一个文件    
- RPM自动处理软件包之间的依赖关系    
- RPM软件包被设计为由“最干净”的源代码而来，从而可以对它重新编译。RPM支持诸如patch这样的Linux工具，可以在编译过程中为软件的源代码打补丁   

### 9.6.1 使用RPM软件包文件    
命名规则: name-version-release.architecture.rpm    
name: 软件包的通用名字，例如mysql     
version: 软件版本号, 如5.0.41    
release: 指定软件包的RPM版本号    
architecture: 指定程序的架构， AMD Athlon: athlon Intel:i386 无特定架构: noarch    

### 9.6.2 安装RPM包     
> rpm -Uhv name-version-release.architecture.rpm  #安装       
> rpm -qa xxx       #查看某个软件包是否已经安装   

### 9.6.3 创建RPM软件包    
参考: [如何制作RPM包](/2016/12/06/rpmbuild-introduction.html)

