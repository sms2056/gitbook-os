# 8. Windows server 2008 R2 分布式文件系统(DFS)

---

## 一. 实验目的
1. 理解分布式文件系统
2. 会使用DFS文件分布式系统

## 二. 实验环境

|软件|版本|
|----|----|
|Vmware Workstation| 12以上 |
|Windows server 2008 DC1(DC和命名空间服务器)| R2 standard,enterprise,datacenter|
|Windows server 2008 DC2(域内主机和DFS复制服务器)| R2 standard,enterprise,datacenter|
|Windows server 2008 DC3(域内主机和DFS复制服务器)| R2 standard,enterprise,datacenter|
|Windows 7(客户机)| 企业版/专业版|



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

### 3. 文件夹和文件夹目标
这些虚拟文件夹的目标分别映射到其他服务器内的公共文件夹,当客户端来浏览文件夹时,DFS会将客户端引导向文件夹目标所映射到的公共文件夹

### 4. DFS复制(DFS Replication)
DFS复制服务,使用一个称为`远程差异压缩(Remote Differential Compression,RDC)`的压缩计算技术,它能够检测文件有改动的地方,因此复制文件时,仅会复制有改动的区域,而不是整个文件,这对带宽有限的网络非常有用

## 五. 复制拓扑

![](/windows/win2008R2/appserver/image/dfs-2.png)

## 六. 实验手册

![](/windows/win2008R2/appserver/image/dfs-1.png)

![](/windows/win2008R2/appserver/image/dfs-3.png)

![](/windows/win2008R2/appserver/image/dfs-4.png)

### a. 设置所有端都进入到域

###### 1. 所有服务器和客户端,都必须加入到域 

Windows server 2008 R2 DC-1:DC(主控)

![](/windows/win2008R2/appserver/image/dfs-5.png)

Windows server 2008 R2 DC-2:域内服务器

![](/windows/win2008R2/appserver/image/dfs-6.png)

Windows server 2008 R2 DC-3:域内服务器

![](/windows/win2008R2/appserver/image/dfs-7.png)

Windows 7:域内客户端

![](/windows/win2008R2/appserver/image/dfs-8.png)

### b. 设置DC端,添加`DFS 命名空间`角色

###### 1. 为DC-1中安装`文件服务器`

![](/windows/win2008R2/appserver/image/dfs-9.png)

###### 2. 在`角色服务`中选择`分布式文件系统` --> 'DFS 命名空间'

![](/windows/win2008R2/appserver/image/dfs-10.png)

###### 3. 在设置`DFS 命名空间`中选择'以后使用服务器管理器中的......'

![](/windows/win2008R2/appserver/image/dfs-11.png)

###### 4. DC端安装`DFS命名服务器`完成

![](/windows/win2008R2/appserver/image/dfs-12.png)

### c. 设置域内另两台server 2008 R2服务器,作为`文件服务器`和`DFS 复制`服务器

###### 1. 添加角色为'DFS 复制'

![](/windows/win2008R2/appserver/image/dfs-13.png)

![](/windows/win2008R2/appserver/image/dfs-14.png)

###### 2. 分别设置同名文件夹的共享,文件夹权限为`任何人`--> `可读可写`

![](/windows/win2008R2/appserver/image/dfs-15.png)

![](/windows/win2008R2/appserver/image/dfs-16.png)

###### 3. 在其中一台`windows server 2008 R2-DC-2`中的共享文件夹内添加一些文件

![](/windows/win2008R2/appserver/image/dfs-17.png)

### d. 设置DC服务器中的'DFS 命名空间',来关联另外两台服务器

###### 1. 打开'DFS Management'
![](/windows/win2008R2/appserver/image/dfs-18.png)

###### 2. 点击`命名空间`,在最右侧找到`创建命名空间...`

![](/windows/win2008R2/appserver/image/dfs-19.png)

###### 3. 在命名空间服务器的`服务器`中填入`DC`服务器的名字,下一步

![](/windows/win2008R2/appserver/image/dfs-20.png)

###### 4. 在`命名空间名称和设置`中填写一个`名称`

![](/windows/win2008R2/appserver/image/dfs-21.png)

###### 5. 在`命名空间类型`中选择'基于域的命名空间'

![](/windows/win2008R2/appserver/image/dfs-22.png)

![](/windows/win2008R2/appserver/image/dfs-23.png)

![](/windows/win2008R2/appserver/image/dfs-24.png)

![](/windows/win2008R2/appserver/image/dfs-25.png)

![](/windows/win2008R2/appserver/image/dfs-26.png)

![](/windows/win2008R2/appserver/image/dfs-27.png)

![](/windows/win2008R2/appserver/image/dfs-28.png)

![](/windows/win2008R2/appserver/image/dfs-29.png)

![](/windows/win2008R2/appserver/image/dfs-30.png)

![](/windows/win2008R2/appserver/image/dfs-31.png)

![](/windows/win2008R2/appserver/image/dfs-32.png)

![](/windows/win2008R2/appserver/image/dfs-33.png)

![](/windows/win2008R2/appserver/image/dfs-34.png)

![](/windows/win2008R2/appserver/image/dfs-35.png)

![](/windows/win2008R2/appserver/image/dfs-36.png)

![](/windows/win2008R2/appserver/image/dfs-37.png)

![](/windows/win2008R2/appserver/image/dfs-38.png)

![](/windows/win2008R2/appserver/image/dfs-39.png)




