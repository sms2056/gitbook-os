# 7. Windows server 2008 R2 网络负载均衡NLB

---

## 一. 实验目的
1. 理解windows server 2008 R2 网络负载均衡
2. 会使用windows server 2008 R2下的网络负载均衡

## 二. 实验环境

|软件|版本|备注
|----|----|----|
|Vmware Workstation| 12以上 ||
|Windows server 2008| R2 standard,enterprise,datacenter|web server + NLB|
|Windows server 2008| R2 standard,enterprise,datacenter|web server + NLB|
|Windows 7| 旗舰版 | 浏览端 |

## 三. 实验相似拓扑图

![](/windows/win2008R2/appserver/image/nlb-1.png)

## 四. 实验手册

### a. 配置两台服务,分配安装`IIS角色`和`负载均衡功能`

![](/windows/win2008R2/appserver/image/nlb-2.png)

![](/windows/win2008R2/appserver/image/nlb-3.png)

### b. 配置dc-1的web服务器为主要负载均衡

![](/windows/win2008R2/appserver/image/nlb-4.png)

![](/windows/win2008R2/appserver/image/nlb-5.png)

![](/windows/win2008R2/appserver/image/nlb-6.png)

![](/windows/win2008R2/appserver/image/nlb-7.png)

![](/windows/win2008R2/appserver/image/nlb-8.png)

![](/windows/win2008R2/appserver/image/nlb-9.png)

![](/windows/win2008R2/appserver/image/nlb-10.png)

![](/windows/win2008R2/appserver/image/nlb-11.png)

![](/windows/win2008R2/appserver/image/nlb-12.png)

![](/windows/win2008R2/appserver/image/nlb-13.png)

![](/windows/win2008R2/appserver/image/nlb-14.png)

![](/windows/win2008R2/appserver/image/nlb-15.png)

![](/windows/win2008R2/appserver/image/nlb-16.png)

![](/windows/win2008R2/appserver/image/nlb-17.png)

![](/windows/win2008R2/appserver/image/nlb-18.png)

![](/windows/win2008R2/appserver/image/nlb-19.png)








