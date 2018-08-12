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

### d. 配置WDS服务器

###### 1. 向服务器中加载`Windows 2008 R2`的光盘镜像

![](/windows/win2008R2/appserver/image/wds-14.png)

###### 2. 打开`服务器管理器` --> `角色` --> `windows部署服务` --> 右击`域名` --> 选择`配置服务器 `

![](/windows/win2008R2/appserver/image/wds-15.png)

###### 3. 输入要一个目录,用于存储相应的镜像文件,建议空间要大

![](/windows/win2008R2/appserver/image/wds-16.png)

###### 4. `DHCP选项`中,什么都不选择

![](/windows/win2008R2/appserver/image/wds-17.png)

###### 5. 设置`PXE 服务器初始设置`,选择`相应所有客户端计算机(已知和未知)`,下面的复选框不选择

![](/windows/win2008R2/appserver/image/wds-18.png)

###### 6. 选择`立即向服务器中添加镜像`

![](/windows/win2008R2/appserver/image/wds-19.png)

###### 7. 在`添加镜像向导`中输入DVD驱动器的路径

![](/windows/win2008R2/appserver/image/wds-20.png)

###### 8. 使用默认的镜像组

![](/windows/win2008R2/appserver/image/wds-21.png)

###### 9. 直接下一步,点击完成

![](/windows/win2008R2/appserver/image/wds-22.png)

![](/windows/win2008R2/appserver/image/wds-23.png)

![](/windows/win2008R2/appserver/image/wds-24.png)

![](/windows/win2008R2/appserver/image/wds-25.png)

![](/windows/win2008R2/appserver/image/wds-26.png)
![](/windows/win2008R2/appserver/image/wds-27.png)
![](/windows/win2008R2/appserver/image/wds-28.png)
![](/windows/win2008R2/appserver/image/wds-29.png)
![](/windows/win2008R2/appserver/image/wds-30.png)
![](/windows/win2008R2/appserver/image/wds-31.png)










