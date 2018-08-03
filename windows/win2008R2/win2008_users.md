# 3. Windows server 2008 R2 账号管理

## 一. 实验目的
1. 可以创建创建用户并对用户进行权限控制
2. 可以创建用户组并将用户放入相应的用户组
3. 单一用户加入多用户组

## 二. 实验环境

|软件|版本|
|----|----|
|Vmware| 14 |
|Windows server 2008 R2|R2 standard,enterprise,datacenter 617598|


## 三.用户概念介绍

```
内置账号 : 系统自带账号,用于完成预定任务
```

```
本机账号 : 创建于本机,只对本机起作用
```

```
域用户账号:创建于DC,对整个网络起作用
```

## 四. 创建本地账号

###### 1. 点击桌面左下角快捷启动栏中的`服务器管理器`

![](/windows/win2008R2/base/image/users-1.png)

###### 2. 单击`服务器管理器`左侧栏的配置,同时右侧栏会有`本地用户和组`的选项

![](/windows/win2008R2/base/image/users-2.png)

###### 3. 双击`本地用户和组`,右侧栏会变为`用户`和`用户组选项`,同时左侧栏的`配置`选项卡的树形结构也被打开

![](/windows/win2008R2/base/image/users-3.png)

###### 4. 双击`用户`,右侧栏就可以看到系统内置账号

![](/windows/win2008R2/base/image/users-4.png)

###### 5. 现在添加账号,在右侧栏空白处单击鼠标右键,选择`新用户`

![](/windows/win2008R2/base/image/users-5.png)

###### 6. 在`新用户`选项卡中填入相关配置,点击创建

![](/windows/win2008R2/base/image/users-6.png)

###### 7. 用户创建成功

![](/windows/win2008R2/base/image/users-7.png)

###### 8. 密码重置,右键点击需要修改的用户账号

![](/windows/win2008R2/base/image/users-8.png)

###### 9. 在弹出的警告框中,点击继续,直接由管理员填写新密码

![](/windows/win2008R2/base/image/users-9.png)

![](/windows/win2008R2/base/image/users-10.png)

###### 10. 用户重命名,用户删除

![](/windows/win2008R2/base/image/users-11.png)

## 五. 创建本地组

###### 1. `服务器管理器` --> `配置` --> `本地用户和组`,右侧栏中可以看到所有用户组及相关的解释说明

![](/windows/win2008R2/base/image/users-12.png)

###### 2. 在右侧栏空白处单击鼠标右键,选择`新建组`

![](/windows/win2008R2/base/image/users-13.png)

###### 3. 在`新建组`选项卡中,填入`组名`,`描述`

![](/windows/win2008R2/base/image/users-14.png)

###### 4. 向新建组中添加成员,点击`添加`,弹出`选择用户`

![](/windows/win2008R2/base/image/users-15.png)

###### 5. 






