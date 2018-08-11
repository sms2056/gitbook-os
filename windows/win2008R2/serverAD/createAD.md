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


