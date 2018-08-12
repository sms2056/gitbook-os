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

###### 3). 必须有DHCP服务器

### b. 在WDS服务器中,安装WDS角色

###### 1. 在`角色`中添加`windows 部署服务`

![](/windows/win2008R2/appserver/image/wds-1.png)

###### 2. 在`角色服务`中,两项全部选中

![](/windows/win2008R2/appserver/image/wds-3.png)

###### 3. WDS安装完成

![](/windows/win2008R2/appserver/image/wds-4.png)

### c. 配置WDS服务器

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

###### 10. 通过`windows 部署服务器`可以看到被抽离的windows`安装镜像`

![](/windows/win2008R2/appserver/image/wds-24.png)

###### 10. 通过`windows 部署服务器`可以看到被抽离的windows`启动镜像`

![](/windows/win2008R2/appserver/image/wds-25.png)

###### 11. 启动同一局域网中的PC,要求BIOS中设置了,使用网络安装系统

![](/windows/win2008R2/appserver/image/wds-34.png)

###### 12. 重新启动客户端,使用WDS服务安装系统

![](/windows/win2008R2/appserver/image/wds-32.png)

### d. 捕获镜像

###### 1. 在`启动镜像`中右键点击`镜像`,选择`创建捕获镜像`

![](/windows/win2008R2/appserver/image/wds-26.png)

###### 2. 输入捕获进行的镜像名称和剥离后镜像的存储位置

![](/windows/win2008R2/appserver/image/wds-27.png)

###### 3. 选择`立即将镜像添加到windows 部署服务器`, 点击完成

![](/windows/win2008R2/appserver/image/wds-28.png)

###### 4. 填入导出的镜像文件

![](/windows/win2008R2/appserver/image/wds-29.png)

###### 5. 默认,直接下一步

![](/windows/win2008R2/appserver/image/wds-30.png)

###### 6. 导入成功

![](/windows/win2008R2/appserver/image/wds-31.png)

###### 7. 客户端双击`sysrep`,用来删除SID等一些环境变量

![](/windows/win2008R2/appserver/image/wds-35.png)

###### 8. 在客户机中设置BIOS,用网络安装系统,进行系统GHO

![](/windows/win2008R2/appserver/image/wds-33.png)