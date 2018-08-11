# 6. Windows server 2008 R2 虚拟化与hyper-v

---

## 一. 实验目的
1. 理解虚拟化
2. 会使用hyper-v

## 二. 实验环境

|软件|版本|
|----|----|
|Vmware Workstation| 12以上 |
|Windows server 2008| R2 standard,enterprise,datacenter|

## 三. hyper-v虚拟化概念
服务器虚拟化能让多个服务器实例在同一台物理主机上同步运行，但各个服务器实例都是相互独立的。 每台虚拟机的运作本质上就像是只有这一台服务器在该物理计算机上运行。 网络虚拟化也有类似的功能，即多个虚拟网络基础结构在同一个物理网络上运行（可能有重叠的 IP 地址），而且每个虚拟网络基础结构的运作就好像只有这一个虚拟网络在此共享的网络基础结构上运行

![](/windows/win2008R2/appserver/image/hyperV-1.png)

在 Hyper-V 网络虚拟化 (HNV) 中，客户被定义为一组部署在数据中心的虚拟机的“拥有者”。 客户可以是多租户公共数据中心的一家公司或企业，或者是私有数据中心的一个部门或业务单位。 每个客户可以在该数据中心有一个或多个 VM 网络，而每个 VM 网络由一个或多个虚拟子网组成。

![](/windows/win2008R2/appserver/image/hyperV-1.jpg)

## 四. 安装Hyper-V前后对比

![](/windows/win2008R2/appserver/image/hyperV-2.png)

## 五. Hyper-V部署模式

### 1. 单击部署

![](/windows/win2008R2/appserver/image/hyperV-4.png)

### 2. 集群部署

![](/windows/win2008R2/appserver/image/hyperV-3.png)

## 六. 实验手册

### a. 安装Hyper-V

###### 1. `服务器管理器` --> `角色` --> `添加角色` --> `Hyper-V`

![](/windows/win2008R2/appserver/image/hyperV-5.png)

### b. 创建虚拟机

###### 1. `服务管理工具` --> `角色` --> `Hyper-V` --> `新建` --> `虚拟机`

![](/windows/win2008R2/appserver/image/hyperV-6.png)

###### 2. 选择创建的虚拟机名称和虚拟机存储位置

![](/windows/win2008R2/appserver/image/hyperV-7.png)

###### 3. 填写要分配的内存大小

![](/windows/win2008R2/appserver/image/hyperV-8.png)

###### 4. 选择网络方式

![](/windows/win2008R2/appserver/image/hyperV-9.png)

###### 5. 选择虚拟磁盘存储的位置及虚拟硬盘大小

![](/windows/win2008R2/appserver/image/hyperV-10.png)

###### 6. 选择以何种方式安装系统

![](/windows/win2008R2/appserver/image/hyperV-11.png)

###### 7. 启动虚拟机

![](/windows/win2008R2/appserver/image/hyperV-12.png)

###### 8. 正常使用

![](/windows/win2008R2/appserver/image/hyperV-13.png)

### c. wmware内使用windows server 2008 R2 的Hyper-V问题

1. 在虚拟机设置中，CPU属性中勾选“Virtualize Intel VT-x/EPT or AMD-V/RVI”来启用虚拟机的CPU支持虚拟化。

![](/windows/win2008R2/appserver/image/hyperV-14.png)

2. 在虚拟机文件所在目录中找到`.vmx`文件

3. 添加如下参数

```
hypervisor.cpuid.v0 = "FALSE"   
mce.enable = "TRUE"
```




