---
title: "Oracle彻底卸载干净教程"
date: 2020-11-04 15:02:25
tags: "oracle"
categories: "Oracle"
---

**参考博客：**<https://blog.csdn.net/a772304419/article/details/79365744>

#### 1.关闭所有服务

​	打开cmd，运行services.msc,关闭oracle所有的服务。

​	![image-20201104184732375](C:\Users\dell\AppData\Roaming\Typora\typora-user-images\image-20201104184732375.png)

#### 2.打开注册表：打开cmd,运行regedit。

 1. 删除 HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ 该路径下所有以oracle开始的服务名称，这个键是标识Oracle在windows下注册的各种服务。

    ![image-20201104184741757](C:\Users\dell\AppData\Roaming\Typora\typora-user-images\image-20201104184741757.png)

 2. 删除：

     HKEY_LOCAL_MACHINE\SOFTWARE\ORACLE

     删除该oracle目录，该目录下注册着Oracle数据库的软件安装信息。

    ![image-20201104184749535](C:\Users\dell\AppData\Roaming\Typora\typora-user-images\image-20201104184749535.png)

 3. 删除注册的oracle事件日志：

    路径：HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Eventlog\Application

    删除注册表的以oracle开头的所有项目。

    ![image-20201104184758069](C:\Users\dell\AppData\Roaming\Typora\typora-user-images\image-20201104184758069.png)

    

    

#### 3.删除环境变量

 鼠标右键右单击"我的电脑-->属性-->高级-->环境变量-->PATH 变量。

  删除Oracle在该值中的内容。注意:path中记录着一堆操作系统的目录，在windows中各个目录之间使用分号（;）隔开的，删除时注意。

![image-20201104184807975](C:\Users\dell\AppData\Roaming\Typora\typora-user-images\image-20201104184807975.png)

#### 4. 重启操作系统

#### 5.删除Oracle_Home下的所有数据。

   （Oracle_Home指Oracle程序的安装目录）

#### 6.删除C:\Program Files下oracle目录。

（该目录视Oracle安装所在路径而定）

#### 7.删除开始菜单下oracle项

如：C:\Documents and Settings\All Users\「开始」菜单\程序\Oracle - Ora10g

   不同的安装这个目录稍有不同。

   如果不删除开始菜单下的Oracle相关菜单目录，没关系，这个不影响再次安装Oracle.当再次安装Oracle时，该菜单会被替换。

至此，Windows平台下Oracle就彻底卸载了。 