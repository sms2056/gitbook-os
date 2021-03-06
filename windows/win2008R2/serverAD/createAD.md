# 1. Windows server 2008 R2 创建AD域

## 一. 实验目的
1. 创建第一个新林
2. 创建在此新林中的第一个域树
3. 创建此新域树中的第一个域
4. 创建此新域中的第一台域控制器

## 二. 实验环境

|软件|版本|
|----|----|
|Vmware Workstation| 12以上 |
|Windows server 2008| R2 standard,enterprise,datacenter|

## 三. 实验拓扑

![](/windows/win2008R2/serverAD/image/createAD-1.png)

## 四. 实验手册

### a. 创建AD域

###### 1. 安装Active Directory域服务(AD DS)

![](/windows/win2008R2/serverAD/image/createAD-2.png)

![](/windows/win2008R2/serverAD/image/createAD-3.png)

![](/windows/win2008R2/serverAD/image/createAD-4.png)

###### 2. 运行`Active Directory域服务安装向导`

![](/windows/win2008R2/serverAD/image/createAD-5.png)

###### 3. 下一步,选择`在新林中新建域`

![](/windows/win2008R2/serverAD/image/createAD-8.png)


![](/windows/win2008R2/serverAD/image/createAD-7.png)

![](/windows/win2008R2/serverAD/image/createAD-6.png)

###### 4. 输入AD域的域名

![](/windows/win2008R2/serverAD/image/createAD-9.png)

###### 5. 选择林功能级别

![](/windows/win2008R2/serverAD/image/createAD-10.png)

###### 6. DC选项

![](/windows/win2008R2/serverAD/image/createAD-11.png)

###### 7. 设置文件存放位置

```
数据文件夹:
用来存储AD数据库
```

```
日志文件文件夹:
用来存储AD的更改日志,此日志文件可以用来修复AD
```

```
SYSVOL文件夹:
用来存储共享文件(如:与组策略有关的文件),注意它必须位于NTFS磁盘内
```

![](/windows/win2008R2/serverAD/image/createAD-12.png)

###### 8. 输入F8下还原模式密码

![](/windows/win2008R2/serverAD/image/createAD-13.png)

###### 9. 安装完成,重启计算机

![](/windows/win2008R2/serverAD/image/createAD-14.png)

![](/windows/win2008R2/serverAD/image/createAD-15.png)

### b. 加入AD域

###### 1. `我的电脑`,右击,选择`属性`,找到`计算机名称.域和工作组设置`,点击`更改设置`

![](/windows/win2008R2/serverAD/image/createAD-16.png)

###### 2. 点击`更改`

![](/windows/win2008R2/serverAD/image/createAD-17.png)

###### 3. 在`隶属于`中,选择`域`,然后属于跟域的域名,点击`确定`,输入管理员名称与密码

![](/windows/win2008R2/serverAD/image/createAD-18.png)

###### 4. 加入成功

![](/windows/win2008R2/serverAD/image/createAD-19.png)

###### 5. 以AD域用户登录

![](/windows/win2008R2/serverAD/image/createAD-20.png)

### c. 脱离AD域

###### 6. 在`隶属于`中,更换回`工作组`,随意输入工作组名称

![](/windows/win2008R2/serverAD/image/createAD-21.png)