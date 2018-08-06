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

###### 4. 在`选择备份配置`界面中需要注意`整个服务器`单选按钮下列出的备份大小，这是用于备份服务器数据、应用程序以及系统状态所需要的存储空间的大小。如果希望备份服务器上所有的卷，选择`整个服务器`单选按钮即可。如果要备份服务器上特定的卷，选中`自定义`单选按钮，单击`下一步`进入设置界面。此时会在`选择备份项目`界面中显示当前服务器所有的卷，在此我们选择需要备份卷,也就是`自定义`，并反选不需要备份的卷对于的选项。需要注意的是，只有NTFS格式的分区才会显示出来，同时包含了引导文件、操作系统文件或应用程序的卷默认会被选中，并且不可取消。

![](/windows/win2008R2/base/image/backup-9.png)

![](/windows/win2008R2/base/image/backup-10-1.png)

![](/windows/win2008R2/base/image/backup-11.png)

###### 5. 依据向导进入`指定备份时间`界面，在此我们可以决定备份的频率和备份的时间。如果希望在每天的特定时间执行备份，需选中`每日一次`单选按钮，然后选择每天进行备份的开始时间。如果希望每台执行多出备份，需选中`每日多此`单选按钮，然后从`可用时间`列表框中选择一个开始时间，并单击`添加`按钮将其加入到`已计划的时间`列表框中，对于每个希望添加的时间，重复上面的操作即可

![](/windows/win2008R2/base/image/backup-12.png)

###### 6. 依据向导进入`选择目标磁盘`界面，在此我们设置保存`备份到卷`,也就是要备份到`D:\`盘。如果要使用的磁盘没有列出，需单击“显示所有可用磁盘”按钮，随后选中复选框，选中每个希望用于保存备份的磁盘。单击“下一步”后，还弹出一个警告对话框，警告我们所选磁盘将会被格式化，现有的数据都会被删除，我们单击“是”即可。
注意 : 每个外部磁盘最多可以包含512个备份，主要取决于每个备份中包含的数据数量。同时在这里还可以选择多个磁盘，这样的话，Windows Server Backup会自动轮换使用目标磁盘进行备份。

![](/windows/win2008R2/base/image/backup-13.png)

![](/windows/win2008R2/base/image/backup-14.png)

![](/windows/win2008R2/base/image/backup-15.png)

###### 7. 点击`下一步`,会显示确认信息,明确标注了备份项目(备份谁),备份目标(备份到哪里)等信息

![](/windows/win2008R2/base/image/backup-16.png)

###### 8. 点击`完成`,将在规定的事件进行数据的备份

![](/windows/win2008R2/base/image/backup-17.png)

###### 9. 不管什么时候执行Windows Server Backup备份服务，该程序都会将相关的事件写入到Windows事件日志中。有关日志可以在`开始` --> `管理工具` --> `事件查看器`的`应用程序和服务日志\Microsof\Windows\Backup\Operational`节点下看到。通过查看Operational日志，我们可以快速了解备份从什么时候开始，什么时候结束，已经失败的原因。

![](/windows/win2008R2/base/image/backup-18.png)

![](/windows/win2008R2/base/image/backup-19.png)

## 五. 系统服务还原

###### 1. 插入Windows Server 2008 R2的光盘，以光盘启动计算机, 点击`下一步`

![](/windows/win2008R2/base/image/backup-20.png)

###### 2. 选择左下角的`修复计算机`

![](/windows/win2008R2/base/image/backup-21.png)

###### 3. 在`系统修复选项`中选择`使用以前创建的系统镜像还原计算机`

![](/windows/win2008R2/base/image/backup-22.png)

![](/windows/win2008R2/base/image/backup-23.png)

![](/windows/win2008R2/base/image/backup-24.png)

![](/windows/win2008R2/base/image/backup-25.png)

































































