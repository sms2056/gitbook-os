工作# 2008活动目录

---

## 1. 概述
Active Directory 域内的Directory是用来存储用户账户,计算机账户等对象,我们把这些对象的存储位置称为目录数据库(Directory Database).Active Directory域内负责提供目录服务的组件就是Active Directory域服务(Active Directory Domain Services, AD DC),它负责目录数据库的存储,添加,删除,修改与查询等工作

## 2. 命名空间
命名空间(Namespace)是一块划分好的区域(Bounded Area),在此区内,我们可以用某个名称来找到与这个名称有关的信息.例如:一个电话本就是一个命名空间.Windows内的文件系统也是一个命名空间.

在Active Directory域服务(AD DS)内,Active Directory就是一个命名空间,利用Active Directory,我们可以通过对象名称来找到与这个对象有关的所有信息

Active Directory域服务与DNS紧密的集成在一起,它的域名空间也是采用DNS架构,因此,域名是采用DNS格式来命名的,如:可以将Active Directory的域名空间为sms2056.com

## 3. 对象与属性
Active Directory域内的资源是以对象(Object)的形式存在,而对象是通过属性(Attribute)来描述其特征,也就是所对象本身是一些属性的集合.

## 4. 容器
容器(Container)与对象相似,它有自己的名称,也有一些属性的集合,不过容器内可以包含其他对象(例如:用户,计算机等对象),还可以包含其他容器,而组织单位(Organization Units OU)是一个比较特殊的容器,其中除了可以包含其他对象与组织单位外,还有组策略(Group Policy)的功能

## 5. 域树









