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

> 密码保护的共享:
> 启用 : 则网络用户连接此计算机时必须先输入有效的用户账号与密码,才可以访问公共文件夹
> 关闭 : 网络用户账户不需要输入账号与密码,就可以访问公共文件夹

![](/windows/win2008R2/base/image/r2share-6.png)

###### 6. 访问共享文件夹,另启用一台虚拟机或实机,网络在同一局域网下,`开始`--> `搜索栏`中输入`\\共享文件夹的IP\`,注意:是`反斜杠`

![](/windows/win2008R2/base/image/r2share-7.png)

###### 7. 输入完成,敲击回车,输入弹出框的用户名密码,就可以进行访问了

![](/windows/win2008R2/base/image/r2share-8.png)

![](/windows/win2008R2/base/image/r2share-9.png)

## 四. 个人文件夹网络共享

###### 1. `D:\`盘,新建一个名为`sms2056`的文件夹,右键点击文件夹,在弹出的菜单中选择`共享` --> `特定用户`

![](/windows/win2008R2/base/image/r2share-10.png)

###### 2. 点击`下拉菜单`,选择相应的用户后点击`添加`,就可以将用户添加到共享目录的用户列表中,点击`共享`

![](/windows/win2008R2/base/image/r2share-11.png)

###### 3. 在弹出的共享方式对话框中,选择默认

![](/windows/win2008R2/base/image/r2share-12.png)

###### 4. 共享成功

![](/windows/win2008R2/base/image/r2share-13.png)

###### 5. 修改共享文件夹名字, 在鼠标移到文件夹,右击鼠标右键,选择`属性`,在文件夹属性对话控中,选择`共享`选项卡,点击`高级共享`,可以修改共享文件夹名字和相关权限

![](/windows/win2008R2/base/image/r2share-14.png)

## 五. 共享文件夹管理

### a. 计算机管理

###### 1. `开始` --> `管理攻击` --> `计算机管理`

![](/windows/win2008R2/base/image/r2share-15.png)

###### 2. `计算机管理` --> '共享文件夹'

> 共享 : 可以查看本地所有的共享文件夹
> 会话 : 可以查看所有链接到共享文件夹的用户及IP
> 打开文件 : 可以查看所有打开过文件的用户及IP

![](/windows/win2008R2/base/image/r2share-16.png)

### b. 共享与存储管理

###### 1. `开始` --> `管理攻击` --> `共享与存储管理`

![](/windows/win2008R2/base/image/r2share-17.png)

## 六. 利用网络驱动器来连接网络计算机

###### 1. 测试远程IP是否有共享文件夹

![](/windows/win2008R2/base/image/r2share-18.png)

###### 2. 双击`计算机` --> 在编辑栏点击`映射网络驱动器`,填入`驱动`和`文件夹`,并勾选`使用其他凭据登录`,点击完成

```
驱动器:
用来连接共享文件夹的驱动器号
```

```
文件夹:
直接输入共享文件夹的UNC(Universal Nameing Convention)路径
也就是\\计算机名或IP地址\共享文件夹名
```
![](/windows/win2008R2/base/image/r2share-19.png)

###### 3. 网络驱动器映射成功

![](/windows/win2008R2/base/image/r2share-20.png)

## 七. 脱机文件设置

###### 1. 已共享的文件夹,鼠标右键,点击`属性`,找到`共享`选项卡,点击`高级共享`

![](/windows/win2008R2/base/image/r2share-21.png)

###### 2. 点击`缓存`,即可进行`脱机设置`

```
1. 仅用户指定的文件和程序可以脱机使用:
用户必须自行从共享文件夹选择希望被缓存到其硬盘的文件,只有被选择文件才可以脱机使用

2. 该共享文件夹的文件或程序在脱机状态下不可用:
表示此共享文件夹不提供脱机使用的功能

3.用户从共享文件夹打开的所有文件和程序自动在脱机状态下可用
只要用户在共享文件夹内访问过的文件,该文件就会自动被缓存到用户的 硬盘内提供脱机使用
```

![](/windows/win2008R2/base/image/r2share-22.png)

## 八. 客户端用户使用脱机文件

Windows 7 客户端默认已经启用了脱机文件,然而Windows Server 2008 R2 必须先安装`桌面体验`功能

###### 1. `开始` --> '管理工具' --> `服务器管理器` --> 左侧栏`功能` --> 点击右侧栏的`添加功能`

![](/windows/win2008R2/base/image/r2share-23.png)

###### 2. 找到`桌面体验`,勾选上,点击下一步,安装,然后按提示重启计算机

![](/windows/win2008R2/base/image/r2share-24.png)

###### 3. 启用脱机文件, '开始' --> `控制面板` --> `同步中心`

![](/windows/win2008R2/base/image/r2share-25.png)

###### 4. 点击`管理脱机文件` --> `启用脱机文件`

![](/windows/win2008R2/base/image/r2share-26.png)

###### 5. 使用脱机可用,进入共享磁盘,鼠标右键点击,选择`始终脱机可用`

![](/windows/win2008R2/base/image/r2share-27.png)

![](/windows/win2008R2/base/image/r2share-28.png)

###### 6. 在`同步中心同`进行脱机文件同步.

![](/windows/win2008R2/base/image/r2share-29.png)

## 卷影副本

###### 1. 对有共享文件夹的磁盘,鼠标右键单击,选择`属性`

![](/windows/win2008R2/base/image/r2share-30.png)

###### 2. 点击相应磁盘,点击`启用`

![](/windows/win2008R2/base/image/r2share-31.png)

###### 3. 按照提示,点击`确认`

![](/windows/win2008R2/base/image/r2share-32.png)

###### 4. 创建成功

![](/windows/win2008R2/base/image/r2share-33.png)

###### 5. 在客户端访问卷影副本, 右键单击文件,选择`属性` --> `以前的版本`

![](/windows/win2008R2/base/image/r2share-34.png)

![](/windows/win2008R2/base/image/r2share-35.png)



