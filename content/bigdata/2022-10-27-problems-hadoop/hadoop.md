---
title: 学习hadoop时遇到的一些问题
author: guoqin77
date: '2022-10-27'
slug: notes-hadoop
categories: []
tags: []
---

## 1 safe mode(安全模式)问题

将本地文件复制到hdfs上去或者在hdfs上新建文件时会出现错误：

`put: Cannot create directory . Name node is in safe mode.`

这是因为hdfs在启动开始时会进入**安全模式**，这时文件系统中的内容不允许修改也不允许删除，直到安全模式结束。

**安全模式**主要是为了系统启动的时候检查各个DataNode上数据块的有效性，同时根据策略必要的复制或者删除部分数据块。运行期通过命令也可以进入安全模式。在实践过程中，系统启动的时候去修改和删除文件也会有安全模式不允许修改的出错提示，只需要等待一会儿即可。

**解决办法：**
可以等待其自动退出安全模式，也可以使用手动命令来离开安全模式：
`hadoop dfsadmin -safemode leave`


## 2 hadoop拒绝访问问题

首先,**检查防火墙是否关闭**，关闭防火墙命令：`systemctl stop firewalld`;

然后,**检查配置文件是否有误**;

在主节点执行 （格式化集群）命令：`hadoop namenode -format`

最后,开启hadoop集群：`start-all.sh`