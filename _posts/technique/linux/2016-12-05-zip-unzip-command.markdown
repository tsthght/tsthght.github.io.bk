---
layout: post
title:  常见的打包解包命令
date:   2016-12-05 21:44:24 +0800
category: 技术
tags:   Linux tar
keywords: zip unzip
description: 
---
# .tar格式   
> 解包：[＊＊＊＊＊＊＊]$ tar xvf FileName.tar    
> 打包：[＊＊＊＊＊＊＊]$ tar cvf FileName.tar DirName（注：tar是打包，不是压缩！）    

# .gz格式     
> 解压1：[＊＊＊＊＊＊＊]$ gunzip FileName.gz   
> 解压2：[＊＊＊＊＊＊＊]$ gzip -d FileName.gz    
> 压 缩：[＊＊＊＊＊＊＊]$ gzip FileName      

# .tar.gz格式    
> 解压：[＊＊＊＊＊＊＊]$ tar zxvf FileName.tar.gz    
> 压缩：[＊＊＊＊＊＊＊]$ tar zcvf FileName.tar.gz DirName     

# .bz2格式     
> 解压1：[＊＊＊＊＊＊＊]$ bzip2 -d FileName.bz2     
> 解压2：[＊＊＊＊＊＊＊]$ bunzip2 FileName.bz2    
> 压 缩： [＊＊＊＊＊＊＊]$ bzip2 -z FileName      

# .tar.bz2格式     
> 解压：[＊＊＊＊＊＊＊]$ tar jxvf FileName.tar.bz2    
> 压缩：[＊＊＊＊＊＊＊]$ tar jcvf FileName.tar.bz2 DirName    

# .bz格式    
> 解压1：[＊＊＊＊＊＊＊]$ bzip2 -d FileName.bz    
> 解压2：[＊＊＊＊＊＊＊]$ bunzip2 FileName.bz    

# .tar.bz格式    
> 解压：[＊＊＊＊＊＊＊]$ tar jxvf FileName.tar.bz   

# .Z格式    
> 解压：[＊＊＊＊＊＊＊]$ uncompress FileName.Z    
> 压缩：[＊＊＊＊＊＊＊]$ compress FileName    

# .tar.Z格式    
> 解压：[＊＊＊＊＊＊＊]$ tar Zxvf FileName.tar.Z   
> 压缩：[＊＊＊＊＊＊＊]$ tar Zcvf FileName.tar.Z DirName    

# .tgz格式   
> 解压：[＊＊＊＊＊＊＊]$ tar zxvf FileName.tgz    

# .tar.tgz格式   
> 解压：[＊＊＊＊＊＊＊]$ tar zxvf FileName.tar.tgz   
> 压缩：[＊＊＊＊＊＊＊]$ tar zcvf FileName.tar.tgz FileName    

# .zip格式    
> 解压：[＊＊＊＊＊＊＊]$ unzip FileName.zip   
> 压缩：[＊＊＊＊＊＊＊]$ zip FileName.zip DirName   

# .lha格式   
> 解压：[＊＊＊＊＊＊＊]$ lha -e FileName.lha    
> 压缩：[＊＊＊＊＊＊＊]$ lha -a FileName.lha FileName     

# .rar格式   
> 解压：[＊＊＊＊＊＊＊]$ rar a FileName.rar   
> 压缩：[＊＊＊＊＊＊＊]$ rar e FileName.rar    

# 参考   
[1] [linux把文件压缩成.tar.gz的命令](https://zhidao.baidu.com/question/72708657.html)     

