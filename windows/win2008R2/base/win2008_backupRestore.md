# 7. Windows server 2008 R2 备份与还原系统

## 一. 实验目的
1. Windows Server Backup 安装
2. 系统备份
3. 系统还原

## 二. 实验环境

|软件|版本|
|----|----|
|Vmware| 14 |
|Windows server 2008 R2|R2 standard,enterprise,datacenter 617598|

## 三. 安装Windows server 2008 R2 下的 Windows Server Backup

###### 1. 点击右下角`服务器管理器`图标,点击左侧树形结构的跟标题`服务器管理器`,在右侧栏中找到`功能摘要`栏,点击下面的`添加功能`

![](/windows/win2008R2/base/image/backup-1.png)

###### 2. 在弹出的`添加功能向导`界面中,选择`Windows Server Backup 功能`,其中包含所有功能,一直下一步,直到安装完成

![](/windows/win2008R2/base/image/backup-2.png)

###### 3. 在`开始` --> `管理工具`,就可以找到刚刚安装好的`Windows Server Backup`

![](/windows/win2008R2/base/image/backup-3.png)

## 四. 备份系统服务

###### 1. `开始` --> `管理工具` --> `Windows Server Backup`或`win + R`,在运行`cmd`中输入Wbadmin.msc,同样可以打开Windows Server Backup管理控制台






