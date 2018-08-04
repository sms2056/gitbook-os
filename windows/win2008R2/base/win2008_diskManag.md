# 6. Windows server 2008 R2 磁盘管理

## 一. 实验目的
1. 启用公共文件夹共享
2. 个人文件夹共享
3. 脱机文件浏览
4. 卷影副本

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












