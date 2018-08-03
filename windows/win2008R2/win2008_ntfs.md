# 4. Windows server 2008 R2 NTFS磁盘管理与安全

## 一. 实验目的
1. 文件/文件夹付权限
2. 
3. 

## 二. 实验环境

|软件|版本|
|----|----|
|Vmware| 14 |
|Windows server 2008 R2|R2 standard,enterprise,datacenter 617598|

## 三. 对文件/文件夹赋权限

###### 1. 创建一个用户

![](/windows/win2008R2/base/image/r8ntfs-1.png)

###### 2. 在`D:`盘创建一个文件夹(sms2056),并在sms2056文件夹中创建一个sms2056的文件

![](/windows/win2008R2/base/image/r8ntfs-3.png)

###### 3. 对`test`文件夹,右键单击`属性`,在弹出的`属性`栏中,`常规`选项卡显示的是文件夹的基本信息

![](/windows/win2008R2/base/image/r8ntfs-2.png)

###### 4. 在`属性`栏中点击`安全`选项卡,可以对文件夹进行用户的权限设置(ALP)

![](/windows/win2008R2/base/image/r8ntfs-4.png)

###### 5. 点击`安全`选项卡中的编辑按钮,弹出'权限管理界面',点击`添加`按钮

![](/windows/win2008R2/base/image/r8ntfs-5.png)

###### 6. 添加刚刚创建的用户.添加完成,点击确认

![](/windows/win2008R2/base/image/r8ntfs-6.png)

###### 7. 对刚刚添加的用户,进行文件夹的权限设置,设置完成,点击确认

![](/windows/win2008R2/base/image/r8ntfs-7.png)

###### 8. 由于继承性,所有`sms056`文件夹下的文件也继承了新用户的权限

![](/windows/win2008R2/base/image/r8ntfs-10.png)

###### 8. 切换到刚刚创建的用户系统下

![](/windows/win2008R2/base/image/r8ntfs-8.png)

![](/windows/win2008R2/base/image/r8ntfs-9.png)

###### 9. 新建用户无法修改由管理员创建的文件

![](/windows/win2008R2/base/image/r8ntfs-11.png)





