---
title: 搭建MPI时遇到的问题
author: guoqin77
date: '2022-11-01'
slug: cloud-problems
categories: []
tags: []
---

#### 1  `sudo apt install mpich`


出现：**sudo: apt：找不到命令**

原因分析：这是由于CentOS的软件安装工具不是apt-get，而是yum，使用yum命令代替apt-get即可。

#### 2  `yum  install mpich`

出现：**已加载插件：fastestmirror**
Determining fastest mirrors

[Errno 14] HTTP Error 404 - Not Found 


[解决方案点这里](https://www.cnblogs.com/yang5726685/p/15662007.html)

#### 3 安装了mpich，却仍旧显示没有mpich?

解决办法：

(1)安装C, C++与Fortran的编译环境:

`yum install make automake gcc gcc-c++ kernel-devel -y`

`yum install  gcc-gfortran -y` 

(2)编译安装:

`wget http://www.mpich.org/static/downloads/3.1.4/mpich-3.1.4.tar.gz`

`mkdir -pv /home/share/mpich`

`tar -xzvf mpich-3.1.4.tar.gz -C /home/share/mpich`

`cd /home/share/mpich/mpich-3.1.4`

`./configure --prefix=/usr/local/mpich`

`make && make install `**这里可能需要加载很久，要等一下。**

(3)安装后加入环境变量到/etc/profile文件:

`vi /etc/profile`

并执行 `source /etc/profile`生效

`PATH=$PATH:/usr/local/mpich/bin`

(4)查看版本信息:

`mpicc -v`

这时可以看到版本信息：mpicc for MPICH version 3.1.4