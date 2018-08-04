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














