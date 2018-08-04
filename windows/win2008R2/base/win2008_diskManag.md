# 6. Windows server 2008 R2 磁盘管理

## 一. 实验目的
1. 会使用磁盘管理工具
2. 
3. 
4. 

## 二. 实验环境

|软件|版本|
|----|----|
|Vmware| 14 |
|Windows server 2008 R2|R2 standard,enterprise,datacenter 617598|

## 三. 基本概念

### 1. MBR和GPT

MBR磁盘: 是标准的传统样式,其`磁盘分区表`是存储在MBR(Master Boot Recrd,主引导记录)内.MBR位于磁盘的最前端,计算机启动时,主板上的BIOS(基本输出/输入系统)会先读取MBR,并将计算机的控制权限交给MBR内的程序,然后由此程序来继续后面的启动工作

GPT磁盘: `磁盘分区表`是存储在GPT(GUID Partition Table)内,他也是位于磁盘的前端,而且他有磁盘分区表和备份磁盘分区表,可提供排错功能,GPT磁盘通过EFI(Extensible Firmware Interface,可扩展固件接口)来作为计算机硬件与操作系统之间通信的桥梁,EFI所扮演的角色类似与MBR磁盘的BIOS

### 2. 基本磁盘和动态磁盘

基本磁盘(Basic Disk)
基本磁盘是传统的磁盘操作系统,在Windows Server 2008 R2内新安装的硬盘`默认`是基本磁盘

动态磁盘(Dynamic Disk)
动态磁盘支持多种特殊的卷,其中有的可以提高系统访问效率,有的可以提供排错功能,有的可以扩大磁盘的使用空间

### 3. 主分区和扩展分区

主分区(Primary Partition)
主分区可以用来启动操作系统,计算机启动时会到活动(Active)的主分区内读取`磁盘分区引导扇区(Partiton Boot Sector)`,然后将控制权交给它来启动相关的操作系统

扩展分区(Extended Partition)
扩展分区只可以被用来存储文件,无法被用来启动操作系统,也就是说,在计算机启动时并不会到扩展分区内读取`磁盘分区引导扇区(Partiton Boot Sector)`

一个MBR磁盘内最多可以创建4个主分区,或最多3个主分区+1个扩展分区

一个GPT磁盘内最多可以创建128个主分区,由于可以多达128个主分区,因此GPT磁盘不需要扩展分区,大于2TB的分区必须使用GPT磁盘


## 四. 基本卷管理工具

###### 1. `开始` --> `管理工具` --> `计算机管理` --> `磁盘管理`

![](/windows/win2008R2/base/image/diskmanage-1.png)

## 五. 压缩卷

###### 1. `磁盘管理` --> 右键点击`c:\` --> 选择`压缩卷`

![](/windows/win2008R2/base/image/diskmanage-2.png)

###### 2. 在`输入压缩空间量`中输入需要压缩的空间量,然后点击`压缩`

![](/windows/win2008R2/base/image/diskmanage-3.png)

###### 3. 成功从系统卷中分出可用空间,`c:\`盘减少空间

![](/windows/win2008R2/base/image/diskmanage-4.png)


## 五. 扩展卷
可以将系统空间扩大,前提是需要有`未分配`的空间

###### 1. `磁盘管理` --> 右键点击`c:\` --> 选择`扩展卷`

![](/windows/win2008R2/base/image/diskmanage-5.png)

###### 2. 在弹出的界面,点击`下一步`

![](/windows/win2008R2/base/image/diskmanage-6.png)

###### 3. 将选择`可用`选项中的磁盘,点击`添加`, 然后下一步 , 最后点击`完成`

![](/windows/win2008R2/base/image/diskmanage-7.png)

###### 4. 成功还原为压缩卷前

![](/windows/win2008R2/base/image/diskmanage-8.png)

## 六. 创建新分区

###### 1. 鼠标右键单击`未分配`的磁盘空间,选择`新建简单卷`

![](/windows/win2008R2/base/image/diskmanage-9.png)

###### 2. 一直下一步,到`分配驱动器号和路径`选项时,按默认处理.

```
分配一下驱动号 : 
代表分析,如`d:\`

装入一下空白NTFS文件夹中 : 
指定一个`空`的NTFS文件夹来代表此分区,则以后所有储存到该文件夹下的文件,都会被存储到此分区
```

![](/windows/win2008R2/base/image/diskmanage-10.png)

###### 3. 按默认格式化分区,直到完成

![](/windows/win2008R2/base/image/diskmanage-11.png)

###### 4. 新分区创建成功

![](/windows/win2008R2/base/image/diskmanage-12.png)

## 七. 转换文件系统

###### 1. 点击桌面左下方`windows PowerShell`图标

![](/windows/win2008R2/base/image/diskmanage-13.png)

###### 2. 执行命令 : `CONVERT H: /FS:NTFS`

![](/windows/win2008R2/base/image/diskmanage-14.png)

## 八. 转化为动态磁盘

###### 1. 动态磁盘分类

a. 简单卷(Simple Volume)
b. 跨区卷(Spanned Volume)
c. 带区卷(Striped Volume)
d. 镜像卷(Mirrored Volume)
e. RAID-5卷(RAID-5 Volume)

其中`简单卷`为动态磁盘的基本单位

|卷种类|需要磁盘数|可用来存储数据的容量|性能|排错|
|----|----|----|----|----|
| 跨区| 2~32个 | 全部 | 不变 | 无 |
| 带区(RAID-0) | 2~32个 | 全部 |读,写都提升许多| 无 |
| 镜像(RAID-1) | 2个 | 一半 | 读提升, 写稍微下降 | 有 |
| RAID-5 | 3~32个 | 磁盘数 - 1| 读提升许多, 写下降稍多 | 有 |

###### 2. 打开虚拟机,找到`windows 2008 R2`的选项卡,点击左则的`Edit virtual machine settings(编辑虚拟机)`

![](/windows/win2008R2/base/image/diskmanage-15.png)

###### 3. 点击`add(添加)` --> `Hard Disk(硬盘)` --> `Next(下一步)` --> 默认到硬盘添加完成

![](/windows/win2008R2/base/image/diskmanage-16.png)

###### 4. 一共添加三块硬盘, 启动虚拟机

![](/windows/win2008R2/base/image/diskmanage-17.png)

###### 5. `开始` --> '管理工具' --> '计算机管理' --> '存储' --> '磁盘管理',可以查看新添加的硬盘,由于没有`连接`所以还不能使用

![](/windows/win2008R2/base/image/diskmanage-18.png)

###### 6. 对每一个新添加的磁盘,都右键点击,选择`联机`

![](/windows/win2008R2/base/image/diskmanage-19.png)

###### 7. 磁盘由原来的`脱机`变为`不可用`

![](/windows/win2008R2/base/image/diskmanage-20.png)





