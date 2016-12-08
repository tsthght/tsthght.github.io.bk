---
layout: post
title: CenOS6.5 下RPM包安装Percona  
date: 2016-12-08 19:22:31 +0800
category: 技术
tags:   mysql
keywords: mysql install
description: 
---
1. 下载RPM包    
官网地址：    
> https://www.percona.com/downloads/Percona-Server-5.5/      

2. 安装的一般顺序       
> rpm -ivh Percona-Server-shared-51-5.1.54-rel12.5.188.rhel5.x86_64.rpm     
> rpm -ivh Percona-Server-devel-51-5.1.54-rel12.5.188.rhel5.x86_64.rpm     
> rpm -ivh Percona-Server-client-51-5.1.54-rel12.5.188.rhel5.x86_64.rpm     
> rpm -ivh Percona-Server-server-51-5.1.54-rel12.5.188.rhel5.x86_64.rpm      

3. 启动服务    
> service mysql start     

4. 登录mysql     
> mysql    

5. 使用grant设置用户     
> grant all privileges on *.* to user@'%' identified by 'xxx';  


