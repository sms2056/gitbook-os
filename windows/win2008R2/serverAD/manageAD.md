# 2. Windows server 2008 R2 AD域的基本管理

---

## 一. 实验目的
1. AD域的基本管理

## 二. 实验环境

|软件|版本|
|----|----|
|Vmware Workstation| 12以上 |
|Windows server 2008| R2 standard,enterprise,datacenter|

## 三.实验手册

### a. AD域管理工具

```
Active Directory用户和计算机
这是以前在Windows Server 2008, Windows Server 2003等系统就已经提供的旧工具
```

![](/windows/win2008R2/serverAD/image/mgrAD-1.png)

```
Active Directory管理中心
这是Windows Server 2008 R2最新工具,用来取代`Active Directory用户和计算机
`
```

![](/windows/win2008R2/serverAD/image/mgrAD-2.png)

### b. 用户相关说明

原本位于本地安全数据库中的本地账号,会在升级后被转移到Active Directory数据库内,而且被放置到Users容器内

这台服务器的计算机账号会被放置到Domain Controllers组织单位内

其他加入域的计算机账户默认会被放置到Computer容器内

### c. 远程管理工具

###### 1. 远程桌面(最高两人)

![](/windows/win2008R2/serverAD/image/mgrAD-4.png)

###### 2. 远程管理工具

![](/windows/win2008R2/serverAD/image/mgrAD-3.png)

Windows 7的远程工具在哪里呢?

