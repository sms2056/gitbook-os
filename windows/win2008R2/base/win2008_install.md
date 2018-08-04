# 1. Windows server 2008 R2 安装实验

## 一. 实验目的
独立完成Windows 2008 R2的系统安装,并明白其中安装中选项的内容

## 二. 实验环境

|软件|版本|
|----|----|
|Vmware Workstation| 12以上 |
|Windows server 2008| R2 standard,enterprise,datacenter|

## 三. 实验步骤

### 0x01 配置windows 2008 R2 虚拟机环境
###### 1. 打开虚拟机,点击`Create a New Virtual Machine`, 下一步.

![](/windows/win2008R2/base/image/vmware-1.png)

###### 2. 在'Virtual Machine Configuration'向导中选择`Custom(advanced)`, 下一步.

![](/windows/win2008R2/base/image/vmware-3.png)

###### 3. 在`hardware compatibility(虚拟机系统兼容性)`中保持默认选项,即本Vmware版本, 下一步

![](/windows/win2008R2/base/image/vmware-4.png)

###### 4. 在`Guest operating System install(客户操作系统安装)`中选择`I will install the operating system later(我将稍后安装操作系统)`, 下一步

![](/windows/win2008R2/base/image/vmware-5.png)

###### 5. 在`Guest operating system(客户操作系统)`向导中选择`1. Microsoft WIndows(微软Windows)`,然后在`version(版本)`中选择`Windows Server 2008 R2 x64`,下一步

![](/windows/win2008R2/base/image/vmware-6.png)

###### 6. 在`Name the Virtual Machine(虚拟机命名)`中,对所创建的虚拟机进行`命名(Name)`和`虚拟机文件存储位置配置(Location)`,在本实验中,使用默认配置

![](/windows/win2008R2/base/image/vmware-7.png)

###### 7. 在`firmware Type(固件类型)`中保持默认,下一步

![](/windows/win2008R2/base/image/vmware-8.png)

###### 8. 在`Processor configuration(处理器配置)`中`Number of process(处理器个数)` 选择 2, `Number of cores per processor(每个处理器的内核数)`选择 2, 下一步

![](/windows/win2008R2/base/image/vmware-9.png)

###### 9. 在`Memery for the Virtual Machine(虚拟机内存配置)`中填写虚拟系统所需内存数量,填写2048,下一步

![](/windows/win2008R2/base/image/vmware-10.png)

###### 10. 在`Network Type(网络类型)`中选择默认类型,下一步

![](/windows/win2008R2/base/image/vmware-11.png)

###### 11. 在'I/O Controller type(I/O控制类型)'中保持默认,下一步

![](/windows/win2008R2/base/image/vmware-12.png)

###### 12. 在`Select a Disk Type(硬盘接口类型)`中保持`默认`选项,下一步

![](/windows/win2008R2/base/image/vmware-13.png)

###### 13. 在`Select a Disk(硬盘存储方式)`中保持默认, 下一步

![](/windows/win2008R2/base/image/vmware-14.png)

###### 14. 在`Specify Disk Capacity(指定磁盘容量)`中,`Maximum disk size(最大磁盘容量)`中填写`100GB`,其他保持默认, 下一步

![](/windows/win2008R2/base/image/vmware-15.png)

###### 15. 在`Specify Disk File(指定虚拟文件名)`中,保持默认配置 下一步

![](/windows/win2008R2/base/image/vmware-16.png)

###### 16. 在`Ready to Create Virtual Machine(查看虚拟机配置)`中,检查所配虚拟机有没有问题,没有问题点击`Finish(完成)`

![](/windows/win2008R2/base/image/vmware-17.png)

###### 17. 虚拟配置完成,图下图

![](/windows/win2008R2/base/image/vmware-18.png)

### 0x02 在虚拟环境中安装windows 2008 R2

###### 1. 点击`VM(虚拟机)`,弹出下拉菜单,选择`settings(配置)`

![](/windows/win2008R2/base/image/vmware-19.png)

###### 2. 在`Virtual Machine Settings(虚拟机配置)`中点击`Hardware(硬件)`选项卡,然后选择其中的`CD/DVD`,在右侧栏中点击`Use ISO image(使用光盘镜像)`,在该单选中,点击`Browse(浏览)`,选择您所存放的`Windows 2008 R2 镜像文件(ISO文件)`,然后点击`Save(保存)`按钮

![](/windows/win2008R2/base/image/vmware-20.png)

###### 3. 点击Vmware软件中的`Start up this guest operating system(启动虚拟机系统)`,进入windows 2008 R2 系统安装界面

![](/windows/win2008R2/base/image/vmware-21.png)

![](/windows/win2008R2/base/image/vmware-22.png)



###### 4. 在Windows 2008 R2安装界面中,点击下一步

![](/windows/win2008R2/base/image/r2install-1.png)

###### 5. 点击`现在安装`,进入下一步

![](/windows/win2008R2/base/image/r2install-2.png)

###### 6. 对所用服务进行选择,这里选择`Windows Server 2008 R2 Enterprise(完全安装)`, 下一步

![](/windows/win2008R2/base/image/r2install-3.png)

###### 7. 接受`许可`, 点击下一步

![](/windows/win2008R2/base/image/r2install-4.png)

###### 8. 在`您想进行何种类型的安装`中选择 `自定义(高级)`

![](/windows/win2008R2/base/image/r2install-5.png)

###### 9. 在`您想将WIndows 安装在何处`中选择 `驱动器选项`

![](/windows/win2008R2/base/image/r2install-6.png)

###### 10. 在`驱动器选项`中点击`新建`,大小填写`40960`, `1024MB * 4 *10 = 40960MB = 40GB` , 点击`应用`, 在后面弹出的对话框中点击`确定`

![](/windows/win2008R2/base/image/r2install-7.png)

![](/windows/win2008R2/base/image/r2install-8.png)

###### 11. 对剩下的未分配空间进行全部分配,操作步骤如第10步

![](/windows/win2008R2/base/image/r2install-9.png)

![](/windows/win2008R2/base/image/r2install-10.png)

###### 12. 点击刚刚创建的`39.9GB`的主分区,用于安装Windows 2008 R2,点击下一步

![](/windows/win2008R2/base/image/r2install-11.png)

###### 13. 系统开始正常安装

![](/windows/win2008R2/base/image/r2install-12.png)

###### 14. 第一次正常登录时,要求修改管理员密码

![](/windows/win2008R2/base/image/r2install-13.png)

![](/windows/win2008R2/base/image/r2install-14.png)

![](/windows/win2008R2/base/image/r2install-15.png)

###### 15. 设置密码成功, 成功进入WIndows 2008 R2


![](/windows/win2008R2/base/image/r2install-16.png)

![](/windows/win2008R2/base/image/r2install-17.png)



























