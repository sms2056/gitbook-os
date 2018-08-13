# 2. Windows server 2008 R2 DNS服务配置与管理

---

## 一. 实验目的
1. 理解DNS服务器查询原理
2. 会配置DNS服务器

## 二. 实验环境

|软件|版本|
|----|----|
|Vmware Workstation| 12以上 |
|Windows server 2008| R2 standard,enterprise,datacenter|

## 三. 基础知识

### a. 域名解析优先级

1. hosts对应的地址
2. 本地DNS服务器
3. 公网DNS服务器


## 三. 安装DNS服务器

###### 1. `服务器管理` --> `添加角色`

![](/windows/win2008R2/appserver/image/dns-1.png)

###### 2. 选择`DNS`服务器

![](/windows/win2008R2/appserver/image/dns-2.png)

###### 3. 安装完成

![](/windows/win2008R2/appserver/image/dns-3.png)

## 四. 配置DNS服务器,使用正向查询,使用户可以正常上网

###### 1. 建立`正向查询`,打开`DNS管理器`,右键点击`正向查找区域`,选择`新建区域`

![](/windows/win2008R2/appserver/image/dns-4.png)

###### 2. 在`区域类型`中,选择`主要区域`

![](/windows/win2008R2/appserver/image/dns-5.png)

###### 3. 输入要创建的`域名`,如:`sms2056.com`

![](/windows/win2008R2/appserver/image/dns-6.png)

###### 4. 在`区域文件`中,选择`创建新文件,文件名为(C):`,按默认就可以

![](/windows/win2008R2/appserver/image/dns-7.png)

###### 5. 在`动态更新`中,选择`不允许动态更新`

![](/windows/win2008R2/appserver/image/dns-8.png)

###### 6. `区域文件`创建完成,右键点击所创建的`区域文件`,选择`新建主机(A或AAAA)(S)...`

![](/windows/win2008R2/appserver/image/dns-9.png)

###### 7. 在`名称`中输入`www`,`IP地址`为目标IP地址,创建`相关的指针(PTR)记录`可以不用选择

![](/windows/win2008R2/appserver/image/dns-10.png)

###### 8. 使用客户机(windows 7),测试DNS是否连通

![](/windows/win2008R2/appserver/image/dns-12.png)

###### 9. 修改客户机DNS为刚配置DNS服务器的地址

![](/windows/win2008R2/appserver/image/dns-11.png)

###### 10. 测试DNS是否可用,测试通过

![](/windows/win2008R2/appserver/image/dns-13.png)

## 五. 配置反向查询

## 六. 通过配置DNS服务器,阻止客户端上指定网址

###### 1. 先在客户端,设置DNS指向DNS服务器,使用浏览器浏览`www.baidu.com`

![](/windows/win2008R2/appserver/image/dns-17.png)

###### 2. 在`DNS`管理器中,设置正向查询

![](/windows/win2008R2/appserver/image/dns-18.png)

###### 3. `区域名称`输入`baidu.com`

![](/windows/win2008R2/appserver/image/dns-19.png)

###### 4. 在`新建区域`中,建立A记录,也就是`新建主机(A 或AAAAA)(S)...`

![](/windows/win2008R2/appserver/image/dns-20.png)

###### 5. 在`名称`中输入`www`,发现`完整限定的域名`为`www.baidu.com`,在`IP地址`处设置为回环地址'127.0.0.1'

![](/windows/win2008R2/appserver/image/dns-21.png)

###### 6. 设置完成

![](/windows/win2008R2/appserver/image/dns-22.png)

###### 7. 清除DNS缓存,发现`www.baidu.com`不能正常访问,实验成功

![](/windows/win2008R2/appserver/image/dns-23.png)

## 七. 使用`转发器`,使用户正常上网

![](/windows/win2008R2/appserver/image/dns-14.png)

![](/windows/win2008R2/appserver/image/dns-15.png)

![](/windows/win2008R2/appserver/image/dns-16.png)

![](/windows/win2008R2/appserver/image/dns-17.png)



## 八.通过委派DNS服务,实现客户端上网










