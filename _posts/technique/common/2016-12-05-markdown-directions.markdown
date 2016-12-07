---
layout: post
title: Markdown 语法学习
date: 2016-12-05 8:49:31 +0800
category: 技术
tags:   markdown
keywords: markdown
description: 
---
![image01](/public/img/markdown-logo.jpg)   

# 标题   
在标题前面添加‘#’号，几级标题就添加几个'#'号   
> \#一级标题  
> \#\#二级标题  
> \#\#\#三级标题   
   
# 列表   
列表分为：有序列表和无序列表，无序列表前加'-'，有序列表前加数字   
> 1. 第一行   
> 2. 第二行   
> 3. 第三行   
   
> \- 文本1   
> \- 文本2   
> \- 文本3   

# 链接和图片   
> \[显示的文本\]\(https://XXX.XXX.XXX\)    
> \!\[  \]\(https://XXX.XXX.XXX\)   

# 引用   
在待引用的文本前加'>'即可   
> \> 引用内容   
 
# 粗体与斜体   
使用一个\*包含的一段文本为*斜体*， 使用两个\*\*包含的一段文本为**粗体**   
> \*斜体\*   
> \*\*粗体\*\*   

# 代码引用   
引用代码时，使用\`将语句抱起来，如果多行，可将\`\`\`置于代码的首行和末行   
> \`hello world\`   
>   
> \`\`\`   
> hello markdown        
> \`\`\`

# 表格   
> \|col1   \|col2  \|col3  \|   

# 转义   
> 使用\\进行转义  

# 生成TOC   
推荐使用Vundle来管理你的Vim插件，基于此前提以下命令可以完成安装:        
1. 在vimrc中添加插件信息     
> Plugin 'mzlogin/vim-markdown-toc'    
2. 安装插件   
> PluginInstall     

使用方法也很简单，将光标移动到想插入Table of Contents的行， 然后运行下面的命令:       
1. :GenTocGFM    
生成GFM连接风格的Table of Contents     
适用于GitHub仓库里的Markdown 文件，也适用于生成GitBook的Markdown文件    
2. :GenTocRedcarpet     
生成Redcarpet连接风格的Table of Contents    
适用于使用Redcarpet作为Markdown引擎的Jekyll项目或其他地方  
  
 
# 参考   
[1] [献给写作者的Markdown新手指南](http://www.jianshu.com/p/q81RER/)   
[2] [markdown语法说明-简体中文版](http://wowubuntu.com/markdown/)   
[3] [为 Markdown 生成 TOC 的 Vim 插件](http://mazhuang.org/2015/12/19/vim-markdown-toc/)   
[4] [Markdown 语法基础及使用教程](http://col.dog/2015/11/22/Markdown-Syntax/)     

