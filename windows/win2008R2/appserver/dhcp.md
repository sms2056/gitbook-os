# 1. Windows server 2008 R2 DHCP服务配置与管理

---

## 一. 实验目的
1. 理解DHCP服务器
2. 会使用DHCP服务器分配IP地址
3. 会使用ipconfig 续租或释放IP地址

## 二. 实验环境

|软件|版本|
|----|----|
|Vmware Workstation| 12以上 |
|Windows server 2008| R2 standard,enterprise,datacenter|

## 三. 实验手册

### a. DHCP的配置

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

###### 8. 启动win 7 客户机获得DHCP分配的地址

### b. IP续租

### c. IP释放


