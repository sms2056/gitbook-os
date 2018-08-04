# 5. Windows server 2008 R2 文件共享系统

## 一. 实验目的
1. 启用公共文件夹共享
2. 个人文件夹共享
3. 脱机文件浏览
4. 卷影副本

## 二. 实验环境

|软件|版本|
|----|----|
|Vmware| 14 |
|Windows server 2008 R2|R2 standard,enterprise,datacenter 617598|

## 三. 公共文件夹共享

###### 1. 查看`公共`文件夹,点击`计算机`或`windows资源管理器` --> `本地磁盘C:(系统盘符)` --> `用户` --> '公共'

![](/windows/win2008R2/base/image/r2share-1.png)

![](/windows/win2008R2/base/image/r2share-2.png)

###### 2. 共享公共文件夹,`控制面板` --> `网络和Internet`

![](/windows/win2008R2/base/image/r2share-3.png)

###### 3. 点击`网络和共享中心`

![](/windows/win2008R2/base/image/r2share-4.png)

###### 4. 进入`网络和共享中心`后,点击左侧的`更改高级共享设置`

![](/windows/win2008R2/base/image/r2share-5.png)

###### 5. 在`高级共享设置`设置中,找到`公共文件夹共享`,点击下面的`启用共享以便可以访问网络的用户可以读取和写入公共文件夹中的文件`

密码保护的共享:
启用 : 则网络用户连接此计算机时必须先输入有效的用户账号与密码,才可以访问公共文件夹

关闭 : 网络用户账户不需要输入账号与密码,就可以访问公共文件夹

![](/windows/win2008R2/base/image/r2share-6.png)

###### 6. 访问共享文件夹,另启用一台虚拟机或实机,网络在同一局域网下,`开始`--> `搜索栏`中输入`\\共享文件夹的IP\`

![](/windows/win2008R2/base/image/r2share-7.png)










