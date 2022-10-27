---
title: problems-blog-establish
author: guoqin77
date: '2022-10-27'
slug: problems-blog-establish
categories: []
tags: []
---

下面记录一下我搭建博客的时候遇到的一些问题吧！


 **[用R语言的blogdown + hugo + netlify + github搭建静态博客系统](https://cloud.tencent.com/developer/news/92522)** 
   
   这里附上一个博主的[视频](https://www.bilibili.com/video/BV1Be4y1h756/?spm_id_from=333.337.search-card.all.click&vd_source=2953fd39e7f1e09be79b878e147450e9)，结合视频可能更清晰。
 
 
## 1 先安装R，再安装Rstudio。
首先我们在安装[R](https://www.r-project.org/)、[Rstudio](https://www.rstudio.com/)和[git](https://git-scm.com/)的时候，应该先安装R，再安装Rstudio，不然有些电脑会出问题。 
## 2 [链接Rstudio链接Git和GitHub并上传文件](https://www.jianshu.com/p/25cd43858f43)
## 3 分支名问题

### (1) git与github库中的分支名不同
当我们打开一个**git.bash**的时候，它默认分支为master,但是我们的github库里面默认的分支是main，这样我们上传文件到github库的时候就会出错，可以**在git里面将分支修改为main**，命令如下：   
`git branch -m oldBranch newBranch`     
上传新命名的本地分支：   
`git push origin newBranch`    


**git更多的用法详见：**      
[Windows下的Git简单使用](https://blog.csdn.net/qq1713802040/article/details/124831253)

### (2) [GitHub分支创建及合并](https://blog.csdn.net/qq_30607843/article/details/84404000)

## 4 pull和push按钮虚化问题  
    
Rstudio制作packge连接github，解决pull和push按钮虚化问题[详情](https://zhuanlan.zhihu.com/p/505604435)。

## 5 .gitignore文件的[创建及使用方法](http://t.zoukankan.com/zz-newbie-p-13219701.html)

我们在git开发中会有一些不愿意提交的目录或者文件，可以通过`.gitignore文件`来忽略不愿意提交的文件。