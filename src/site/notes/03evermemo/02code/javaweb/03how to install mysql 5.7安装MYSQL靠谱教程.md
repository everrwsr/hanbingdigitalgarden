---
{"dg-publish":true,"permalink":"/03evermemo/02code/javaweb/03how to install mysql 5.7安装MYSQL靠谱教程/","dgPassFrontmatter":true}
---


# [Windows安装MySQL5.7教程](https://www.cnblogs.com/kendoziyu/p/MySQL.html)

https://www.cnblogs.com/kendoziyu/p/MySQL.html

**导读：**  
我们日常学习可能会需要在**本地安装MySQL服务**，也遇到过小伙伴探讨关于Windows系统安装MySQL的问题。在这里建议大家安装**MySQL5.7版本**，当然想尝试8.0版本的同学也可以参考安装。本篇文章以在Windows7（64位）系统安装MySQL5.7.27为例，一步步的为大家总结出安装步骤，希望对大家有所帮助！

### 一、检查及卸载原版本

我们可以检查下我们的系统服务确定下有没有安装过MySQL，打开Windows系统服务有以下两种方式：

-   右击我的电脑/计算机，点击管理，打开计算机管理，依次选择服务和应用程序——服务。
-   使用快捷命令：同时按下**win+r键**，在运行窗口中输入**services.msc**，即可打开服务。

打开系统服务后页面如下，可以看到我的电脑中已经安装有MySQL，下面我将其卸载，若你的电脑没有MySQL服务则不需要操作此步。  
![检查Mysql服务](https://img2018.cnblogs.com/blog/1730512/201910/1730512-20191002105417276-217001891.png "检查Mysql服务")

现在我们打开cmd命令行来卸载MySQL：

1.停止MySQL服务  
![停止Mysql服务](https://img2018.cnblogs.com/blog/1730512/201910/1730512-20191002105456062-1583359584.png "停止Mysql服务")  
2.卸载MySQL  
![卸载Mysql](https://img2018.cnblogs.com/blog/1730512/201910/1730512-20191002105524805-457396218.png "卸载Mysql")

### 二、下载MySQL安装包

我们常用的是**MySQL Community Server**这款产品。

##### 下载方案A：

> 下载地址（选择该地址可下载目前最新的通用版本）：  
> [https://dev.mysql.com/downloads/mysql/](https://dev.mysql.com/downloads/mysql/)

1.  点击`Looking for previous GA versions`，点击后效果如下图，：  
    ![查找最新的通用版本](https://img2018.cnblogs.com/blog/1730512/201910/1730512-20191002105603734-976233778.png "查找最新的通用版本")
    
2.  有两种可选的下载策略，一个是下载installer安装器，一个是下载解压安装包  
    ![](https://img2018.cnblogs.com/blog/1730512/201910/1730512-20191002105718006-80264316.png)
    
3.  installer安装器下载地址:
    

> [https://dev.mysql.com/downloads/windows/installer/5.7.html](https://dev.mysql.com/downloads/windows/installer/5.7.html)

![下载安装器](https://img2018.cnblogs.com/blog/1730512/201910/1730512-20191002105747162-1277733805.png)

PS:只有32位的下载器

##### 下载方案B：

> 下载地址（选择该地址可以下载历史版本）  
> [https://downloads.mysql.com/archives/community/](https://downloads.mysql.com/archives/community/)

PS：选择这种方式**只能下载用压缩包方案**安装。

![](https://img2018.cnblogs.com/blog/1730512/201910/1730512-20191002105836291-1834009670.png)

### 三、安装MySQL

##### 安装方案A：安装器安装

###### 1. 双击安装包mysql-installer-community-5.7.27.0.msi时出现错误

![installer安装报错](https://img2018.cnblogs.com/blog/1730512/201910/1730512-20191003122859389-1971663578.png)

> 下载.NET FRAMEWORK 4.5.2的地址 [https://www.microsoft.com/zh-CN/download/details.aspx?id=42642](https://www.microsoft.com/zh-CN/download/details.aspx?id=42642)

###### 2. 选择安装类型Server Only

![Server Only](https://img2018.cnblogs.com/blog/1730512/201910/1730512-20191003123008831-453269682.png)

选择理由：我的主要目的不是对MySQL进行二次开发，而是基于MySQL提供的数据库服务，开发Web服务器，所以选择选择Server Only。

###### 3. 遇到缺少必要的组件：

![Check Requirements](https://img2018.cnblogs.com/blog/1730512/201910/1730512-20191003123041760-1437047115.png)

-   Microsoft Visual C++ 2013 Redistributable Packages（x64） is not installed

> 下载地址：[https://www.microsoft.com/en-us/download/details.aspx?id=40784](https://www.microsoft.com/en-us/download/details.aspx?id=40784)

-   我选择了下载 vcredist_x64.exe
-   双击安装 vcredist_x64.exe，安装完成之后，关闭MySQL Intaller并重新打开  
    ![MySQL-installation](https://img2018.cnblogs.com/blog/1730512/201910/1730512-20191003123120007-1732055678.png)

###### 4. 其他的一些步骤参考（基本保持默认,点击Next就好了）

![High-availability](https://img2018.cnblogs.com/blog/1730512/201910/1730512-20191003123202668-1358491620.png)  
![Type-and-networking](https://img2018.cnblogs.com/blog/1730512/201910/1730512-20191003123235586-1307104687.png)  
这一步选择填写数据库的端口号  
![Windows Service](https://img2018.cnblogs.com/blog/1730512/201910/1730512-20191003123333492-1449855759.png)  
这一步填写Windows服务的名称  
![Apply Configurations](https://img2018.cnblogs.com/blog/1730512/201910/1730512-20191003123400271-794557846.png)  
这一步自动依次执行列表中所有的额外配置步骤

###### 5. 配置环境变量

我的MySQL安装在`C:\Program Files\MySQL\MySQL Server 5.7`目录下，

-   在桌面上右击计算机-属性-高级系统设置：  
    ![环境变量](https://img2018.cnblogs.com/blog/1730512/201910/1730512-20191003123443242-709003050.png)  
    **新增** 系统变量MYSQL_HOME=C:\Program Files\MySQL\MySQL Server 5.7  
    在系统变量Path的最后 **追加** `;%MYSQL_HOME%\bin`
    
-   `Win+R`打开运行，输入`cmd`回车  
    ![Cmd-Windows-Service](https://img2018.cnblogs.com/blog/1730512/201910/1730512-20191003123504019-1764572605.png)
    

##### 安装方案B：解压安装包安装

###### 1.解压安装包（mysql-5.7.17-winx64）

> 我选择解压在D盘，并且创建lib文件夹，即D:\lib\mysql-5.7.17-winx64，我又修改文件夹名称为D:\lib\mysql  
> ![解压MySQL](https://img2018.cnblogs.com/blog/1730512/201910/1730512-20191007001628194-2037607139.png)

###### 2.在解压目录下创建my.ini

```csharp
[client]
# 设置mysql客户端默认字符集
default-character-set=utf8

[mysqld]
# 设置3306端口
port=3306
character_set_server=utf8
# 解压目录
basedir=D:\lib\mysql
# 解压目录下data目录
datadir=D:\lib\mysql\data
default-storage-engine=INNODB

sql_mode=NO_ENGINE_SUBSTITUTION,STRICT_TRANS_TABLES

[WinMySQLAdmin]
D:\lib\mysql\bin\mysqld.exe

```

###### 3.设置MYSQL的环境变量

-   新增系统变量 MYSQL_HOME=D:\lib\mysql
-   在系统变量Path后面追加`;%MYSQL_HOME%\bin`

###### 4.安装MYSQL

-   在解压目录的\bin下（D:\lib\mysql\bin)，按住键盘`Ctrl+Shift`，然后右击鼠标打开命令窗口  
    ![打开命令窗口](https://img2018.cnblogs.com/blog/1730512/201910/1730512-20191007001651827-785308498.png)
    
-   执行命令初始化数据库  
    `mysqld -install`  
    `mysqld --initialize --console`  
    ![初始化数据库](https://img2018.cnblogs.com/blog/1730512/201910/1730512-20191007001732043-1502848367.png)
    

> “mysqld --initialize --console”命令，可以得到mysql的初始密码，用**mysqld  --initialize 的目的是**初始化data目录。要不然mysql5.7的解压文件夹下面不会出现data文件夹  
> 比如本文中的初始密码为`.ak8%if5#nzJ`

-   接着就是在输入**net start mysql**启动服务
-   开始使用mysql，输入命令：**mysql -uroot -p**，然后输入刚才的初始密码
-   修改密码  
     `mysql> alter user 'root'@'localhost' identified by '123456';`  
    `mysql> flush privileges;`
-   使用quit退出
-   输入命令：**mysql -uroot -p**，然后尝试新密码

参考：  
[https://blog.51cto.com/10814168/2402109](https://blog.51cto.com/10814168/2402109)

