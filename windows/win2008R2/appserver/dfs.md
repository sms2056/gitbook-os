# 8. Windows server 2008 R2 分布式文件系统(DFS)

---

## 一. 实验目的
1. 理解分布式文件系统
2. 会使用DFS文件分布式系统

## 二. 实验环境

|软件|版本|
|----|----|
|Vmware Workstation| 12以上 |
|Windows server 2008| R2 standard,enterprise,datacenter|

## 三. 概述

`分布式文件系统(Distributed File System, DFS)`可以提高文件的访问效率,提高文件的可用性和减轻服务器的负担

## 四. DFS的一般架构
Windows Server 2008 R2是通过`文件服务`角色内的`DFS命名空间`和`DFS复制`这两个服务来创建DFS的

![](/windows/win2008R2/appserver/image/dfs-1.png)

