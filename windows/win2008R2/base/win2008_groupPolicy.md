# 8. Windows server 2008 R2 组策略和本地策略

## 一. 实验目的
1. 会用常用的组策略

## 二. 实验环境

|软件|版本|
|----|----|
|Vmware| 14 |
|Windows server 2008 R2|R2 standard,enterprise,datacenter 617598|

## 三. 组策略工具使用

### 方式一: 打开`本地计算机策略`

###### 1. `开始` --> `管理工具` --> `本地安全策略`

![](/windows/win2008R2/base/image/grouppolicy-1.png)

### 方式二: 打开`本地安全策略`

###### 1. '开始' --> 搜索栏输入`GPEDIT.MSC`


![](/windows/win2008R2/base/image/grouppolicy-2.png)

## 四. 使用`本地安全策略`配置计算机安全属性

### 1). 使用策略关闭`关机理由`

###### `计算机配置` --> `管理模板` --> `系统` --> 双击右栏的`显示关闭事件跟踪程序` --> 选择`已禁用`

![](/windows/win2008R2/base/image/grouppolicy-3.png)

![](/windows/win2008R2/base/image/grouppolicy-4.png)

### 2). 删除开始菜单中的关机,重新启动,睡眠和休眠命令

###### `用户配置` --> `管理模板` --> `开始菜单和任务栏` --> 双击右侧栏的`删除并阻止访问关机,重新启动,睡眠和休眠` --> 选择`已启用` --> `确定`

![](/windows/win2008R2/base/image/grouppolicy-5.png)

![](/windows/win2008R2/base/image/grouppolicy-6.png)

###### 配置成功

![](/windows/win2008R2/base/image/grouppolicy-7.png)

### 3). 删除IE浏览器的`Internet选项`内的`安全与连接`标签

###### `用户配置` --> `管理模板` --> `Windows组件` --> `Internet Explorer` --> `Internet控制面板` --> 将`禁用连接页`和`禁用安全页`设为`已启用`
![](/windows/win2008R2/base/image/grouppolicy-11.png)

###### 策略前

![](/windows/win2008R2/base/image/grouppolicy-8.png)

![](/windows/win2008R2/base/image/grouppolicy-9.png)

###### 策略后

![](/windows/win2008R2/base/image/grouppolicy-10.png)

### 4). 将控制面板内的Windows防火墙隐藏起来

###### `用户配置` --> `管理模板` --> `控制面板` --> 双击右侧栏的 `隐藏指定的控制面板` -->



















 
