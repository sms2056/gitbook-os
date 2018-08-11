# 2. Windows server 2008 R2 AD域的基本管理

---

## 一. 实验目的
1. AD域的基本管理

## 二. 实验环境

|软件|版本|
|----|----|
|Vmware Workstation| 12以上 |
|Windows server 2008| R2 standard,enterprise,datacenter|

## 三.实验手册

### a. AD域管理工具

```
Active Directory用户和计算机
这是以前在Windows Server 2008, Windows Server 2003等系统就已经提供的旧工具
```

![](/windows/win2008R2/serverAD/image/mgrAD-1.png)

```
Active Directory管理中心
这是Windows Server 2008 R2最新工具,用来取代`Active Directory用户和计算机
`
```

![](/windows/win2008R2/serverAD/image/mgrAD-2.png)

### b. 用户相关说明

原本位于本地安全数据库中的本地账号,会在升级后被转移到Active Directory数据库内,而且被放置到Users容器内

这台服务器的计算机账号会被放置到Domain Controllers组织单位内

其他加入域的计算机账户默认会被放置到Computer容器内

### c. 远程管理工具

###### 1. 远程桌面(最高两人)

![](/windows/win2008R2/serverAD/image/mgrAD-4.png)

###### 2. 远程管理工具

![](/windows/win2008R2/serverAD/image/mgrAD-3.png)

Windows 7的远程工具在哪里呢?

### d. 新建组织和单位

###### 1. 'Active Directory用户和计算机',右键点击一个DC控制器,选择`新建` --> `组织单位`

![](/windows/win2008R2/serverAD/image/mgrAD-5.png)

###### 2. 输入组织单位的名称

![](/windows/win2008R2/serverAD/image/mgrAD-6.png)

###### 3. 创建`组织单位`成功

![](/windows/win2008R2/serverAD/image/mgrAD-7.png)

### e. 新建用户

###### 1. 找到要创建用户的`组织单位`,鼠标右键,选择`用户`


![](/windows/win2008R2/serverAD/image/mgrAD-8.png)

###### 2. 填写相关信息,在同一域中,`用户登录名`必须唯一

![](/windows/win2008R2/serverAD/image/createAD-22.png)

###### 3. 填写`密码`,用户设置完毕

![](/windows/win2008R2/serverAD/image/mgrAD-9.png)

###### 4. 以新建`用户`,登录域内的计算机

![](/windows/win2008R2/serverAD/image/mgrAD-10.png)

### f. 赋予用户在域控制器上具备`允许本地登录`的权限

###### 1. `开始` --> `管理工具` --> `sushi2056.com` --> `Domain Controllers`,右键点击`Default Domain Controllers Policy`,点击`编辑`

![](/windows/win2008R2/serverAD/image/mgrAD-11.png)

###### 2. 











