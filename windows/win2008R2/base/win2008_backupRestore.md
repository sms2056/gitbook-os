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

![](/windows/win2008R2/base/image/backup-4.png)

![](/windows/win2008R2/base/image/backup-5.png)

初次使用Windows Server Backup时，我们会看到一条警告信息说这台计算机上还没有配置备份。如果要清除该警告，只需要使用“一次性备份”功能创建一个备份，或者使用备份计划功能自动创建备份即可。

![](/windows/win2008R2/base/image/backup-6.png)

###### 2. 在备份之前可以设置“配置性能设置”

在使用Windows Server Backup时，对服务器的首次备份将是完整备份。这是因为完整备份会清除所有文件的存档位，这样Windows Server Backup就可以跟踪对文件的后续修改。随后Windows Server Backup要执行完整或增量备份则取决于配置的默认性能设置

```
普通备份性能:
备份整体数据,不会与源数据对比,所以性能不变,但是存储增大

快速备份性能(增量备份):
档次备份与上次备份进行对比,选择更改过的数据备份,由于存在对比,服务期性能下降,但是存储增长不多,"修改多少涨多少"

```

![](/windows/win2008R2/base/image/backup-7.png)

###### 3. 在右侧栏选择`备份计划`或菜单栏中点击`操作”下拉菜单中选择“备份计划”就会启动备份计划向导。在扫描完所有可用磁盘后，Windows Server Backup会启动备份计划向导,单击“下一步”。

![](/windows/win2008R2/base/image/backup-8.png)

###### 4. 在“选择备份配置”界面中需要注意“整个服务器”单选按钮下列出的备份大小，这是用于备份服务器数据、应用程序以及系统状态所需要的存储空间的大小。如果希望备份服务器上所有的卷，选择“整个服务器”单选按钮即可。如果要备份服务器上特定的卷，选中“自定义”单选按钮，单击“下一步”进入设置界面。此时会在“选择备份项目”界面中显示当前服务器所有的卷，在此我们选择需要备份卷,也就是`自定义`，并反选不需要备份的卷对于的选项。需要注意的是，只有NTFS格式的分区才会显示出来，同时包含了引导文件、操作系统文件或应用程序的卷默认会被选中，并且不可取消。

![](/windows/win2008R2/base/image/backup-9.png)

![](/windows/win2008R2/base/image/backup-10.png)

![](/windows/win2008R2/base/image/backup-11.png)












