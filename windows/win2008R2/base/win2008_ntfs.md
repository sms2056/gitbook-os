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

## 四. 数据压缩

###### 1. 在`D:`创建一个名为`sms056`的文件夹

![](/windows/win2008R2/base/image/r8ntfs-12.png)

###### 2. 对`sms2056`文件夹单击鼠标右键,选择属性

![](/windows/win2008R2/base/image/r8ntfs-13.png)

###### 3. 在`常规`选项卡中,点击高级

![](/windows/win2008R2/base/image/r8ntfs-14.png)

###### 4. 在`高级属性`中选择`压缩内容以便节省磁盘空间`,点击确定

![](/windows/win2008R2/base/image/r8ntfs-15.png)

###### 5. 若创建的文件夹内存在文件或文件夹,则会有如下图选项

```
仅将更改应用到此文件夹:
在此文件夹内所新建的文件,子文件夹与子文件夹内的文件都会被自动压缩
但是并不会影响到子文件夹内现有的文件与文件夹
```

```
将更改应用与此文件夹,子文件夹和文件:
在此文件夹内所新建的文件,子文件夹与子文件夹内部的文件都会被自动压缩.
同时会将已经保存在此文件夹内的现有文件,子文件夹与子文件夹内的文件一起压缩
```

![](/windows/win2008R2/base/image/r8ntfs-16.png)

###### 6. 若文件夹,压缩后,文件夹外观无颜色变化,则可以在`文件夹和搜索选项`中进行修改

![](/windows/win2008R2/base/image/r8ntfs-18.png)

![](/windows/win2008R2/base/image/r8ntfs-17.png)

###### 注意: 

已经加密的文件或文件夹,无法压缩,反过来一样

## 五. 文件压缩/文件夹压缩

###### 1. 在`D:\`新建一个名为`sms2056`的文件夹,在文件夹内随意创建一个文件, 并鼠标右键单击文件夹,选择发送到`压缩(zippad)文件夹`

![](/windows/win2008R2/base/image/r8ntfs-19.png)

###### 2. 压缩文件创建成功

![](/windows/win2008R2/base/image/r8ntfs-20.png)

## 六. 文件加密

###### 1. 在`D:\`新建一个名为`sms2056`的文件夹,在文件夹内随意创建一个文件, 并鼠标右键单击文件夹,选择`属性`,在`属性`选项卡中点击`高级`

![](/windows/win2008R2/base/image/r8ntfs-22.png)

###### 2. 在`高级属性`中点击`加密内容以便保护数据`,利用windows自带证书系统对文件夹进行加密

![](/windows/win2008R2/base/image/r8ntfs-23.png)

###### 3. 查看加密文件夹中文件的可访问人

![](/windows/win2008R2/base/image/r8ntfs-24.png)

###### 4. 其他用户访问该文件,会被拒绝

![](/windows/win2008R2/base/image/r8ntfs-25.png)

![](/windows/win2008R2/base/image/r8ntfs-26.png)

###### 5. 证书备份, 在`certmgr.msc`中点击`个人证书`,然后导出备份

![](/windows/win2008R2/base/image/r8ntfs-21.png)

###### 6. 其他用户可以访问被加密的文件方式

1. 用户必须具有EFS证书,才可以被授权,而一般用户在第一次执行加密操作后,他就会被自动服务EFS证书,也就可以被授权了,因此,可以先让其他用户进行一次加密操作.

2. 具有修复证书的用户也可以访问被加密的文件,默认只有域Administrator拥有修复证书的权限,不过可以通过组策略或本地策略来将`修复证书`分配给其他用户