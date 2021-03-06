---
title: Oracle---数据库、实例、用户、表空间、表之间的关系讲解 
tags: Oracle
grammar_cjkRuby: true
---

#  基本概念

 - 数据库

Oracle数据库是数据的物理存储。这就包括（数据文件ORA或者DBF、控制文件、联机日志、参数文件）,它是**物理文件的集合**。

 - 实例

实例是访问Oracle数据库所需的一部分计算机内存和辅助处理后台进程，是由**进程和这些进程所使用的内存**(SGA)所构成一个集合。一个数据库可以有n个实例。

 - 用户

用户是在实例下建立的。不同实例可以建相同名字的用户。就是一个登陆的名，当然得有密码，它跟**表空间是多对多**的关系的，但我们在创建用户时一般都指定默认表空间的，若不指定用户默认表空间的话，则用户每次创建数据库对象的时候，都要指定表空间，太麻烦

 - 表空间

表空间是一个用来管理数据存储逻辑概念，表空间只是和数据文件（ORA或者DBF文件）发生关系，数据文件是物理的，一个表空间可以包含多个数据文件，而一个数据文件只能隶属一个表空间。

 - 数据文件（dbf、ora）
 
数据文件是数据库的物理存储单位。数据库的数据是存储在表空间中的，真正是在某一个或者多个数据文件中。而一个表空间可以由一个或多个数据文件组成，一个数据文件只能属于一个表空间。一旦数据文件被加入到某个表空间后，就不能删除这个文件，如果要删除某个数据文件，只能删除其所属于的表空间才行。

 - 角色

每个用户都有角色，它决定了该用户有什么权限，比如DBA，拥有最高权限

 - 表
  
一个表只能属于一个表空间


# 关系示意图
![enter description here][1]


# 备注
 

 1. 实例与数据库的辩证关系：
    实例用于管理和控制数据库；而数据库为实例提供数据。一个数据库可以被多个实例装载和打开；而一个实例在其生存期内只能装载和打开一个数据库。
 2. 用户和表空间相互之间并没有归属关系，要建1个用户、N个表空间 或是N个用户、1个表空间 都是可以的.

  [1]: ./images/%E5%9F%BA%E7%A1%80%E6%A6%82%E5%BF%B5.jpg "基础概念"