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

### 1. DFS命名空间(DFS Namespace)
通过`DFS命名空间`将位于不同服务器内的共享文件夹组合在一起,并以一个虚拟文件夹的树状结构显示给客户端.

DFS命名空间分为两种:
1. 域命名空间
2. 独立命名空间

### 2. 命名空间根目录(Namespace Root)
它是命名空间的起始点此根目录的名称为public,命名空间的名称为\\sayms.com\public,而且它是一个域命名空间,其名称是以域名开头.如果这是一个独立命名空间,则命名空间的名称会以计算机名开头,如\\server\public