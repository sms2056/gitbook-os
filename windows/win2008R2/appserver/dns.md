# 2. Windows server 2008 R2 DNS服务配置与管理

---

## 一. 实验目的
1. 理解DNS服务器查询原理
2. 会配置DNS服务器

## 二. 实验环境

|软件|版本|
|----|----|
|Vmware Workstation| 12以上 |
|Windows server 2008| R2 standard,enterprise,datacenter|

## 三. 安装DNS服务器

###### 1. `服务器管理` --> `添加角色`

![](/windows/win2008R2/appserver/image/dns-1.png)

###### 2. 选择`DNS`服务器

![](/windows/win2008R2/appserver/image/dns-2.png)

###### 3. 安装完成

![](/windows/win2008R2/appserver/image/dns-3.png)

## 四. 配置DNS服务器,使用户可以正常上网

###### 1. 建立`正向查询`,打开`DNS管理器`,右键点击`正向查找区域`,选择`新建区域`

![](/windows/win2008R2/appserver/image/dns-4.png)

###### 2. 在`区域类型`中,选择`主要区域`

![](/windows/win2008R2/appserver/image/dns-5.png)

###### 3. 输入要创建的`域名`,如:`sms2056`

![](/windows/win2008R2/appserver/image/dns-6.png)

![](/windows/win2008R2/appserver/image/dns-7.png)

![](/windows/win2008R2/appserver/image/dns-8.png)

![](/windows/win2008R2/appserver/image/dns-9.png)

![](/windows/win2008R2/appserver/image/dns-10.png)

![](/windows/win2008R2/appserver/image/dns-11.png)

![](/windows/win2008R2/appserver/image/dns-12.png)

![](/windows/win2008R2/appserver/image/dns-13.png)










