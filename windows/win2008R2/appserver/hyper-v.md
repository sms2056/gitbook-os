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

![](/windows/win2008R2/appserver/image/hyperV-2.png)





### 2. 集群部署

![](/windows/win2008R2/appserver/image/hyperV-2.png)



