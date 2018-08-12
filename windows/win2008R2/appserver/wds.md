# 9. Windows server 2008 R2 Windows部署服务(WDS)

---

## 一. 实验目的
1. 理解WDS
2. 会使用WDS进行有人值守安装

## 二. 实验环境

|软件|版本|
|----|----|
|Vmware Workstation| 12以上 |
|Windows server 2008| R2 standard,enterprise,datacenter|

## 三. 实验手册

### a. 前期准备

###### 1). 配置完成的AD域

![](/windows/win2008R2/appserver/image/wds-1.png)

###### 2). WDS服务器必须加入AD域(该实验中,域和WDS同在一台服务器中)

### b. 在WDS服务器中,安装WDS角色

###### 1. 在`角色`中添加`windows 部署服务`

![](/windows/win2008R2/appserver/image/wds-1.png)

###### 2. 在`角色服务`中,两项全部选中

![](/windows/win2008R2/appserver/image/wds-3.png)

###### 3. WDS安装完成

![](/windows/win2008R2/appserver/image/wds-4.png)

### c. 安装DHCP服务器,用于网络系统安装

###### 1. 在`角色`中添加`windows 部署服务`






