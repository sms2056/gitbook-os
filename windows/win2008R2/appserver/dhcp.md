# 1. Windows server 2008 R2 DHCP服务配置与管理

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

### c. 安装DHCP服务器,用于网络系统安装

###### 1. 在`角色`中添加`DHCP服务器`

![](/windows/win2008R2/appserver/image/wds-5.png)

###### 2. 要绑定本服务器IP地址

![](/windows/win2008R2/appserver/image/wds-6.png)

###### 3. 对父域和首选DNS进行设置

![](/windows/win2008R2/appserver/image/wds-7.png)

###### 4. 设置不需要WINS服务

![](/windows/win2008R2/appserver/image/wds-8.png)

###### 4. 设置DHCP的作用于,也就是要分配的IP段

![](/windows/win2008R2/appserver/image/wds-9.png)

![](/windows/win2008R2/appserver/image/wds-10.png)

###### 5. 不需要IPv6的DHCP分配

![](/windows/win2008R2/appserver/image/wds-11.png)

###### 6. 设置DHCP服务器授权,以默认为主

![](/windows/win2008R2/appserver/image/wds-12.png)

###### 7. 配置完成

![](/windows/win2008R2/appserver/image/wds-13.png)



