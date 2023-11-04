---
{"dg-publish":true,"permalink":"/03evermemo/02code/Window 下 Redis 的安装和部署详细图文教程（Redis 的安装和可视化工具的使用未命名/","dgPassFrontmatter":true,"noteIcon":"","created":"","updated":""}
---

> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [blog.csdn.net](https://blog.csdn.net/weixin_44893902/article/details/123087435)



### 文章目录

*   [Redis 下载地址：](#Redis_6)
*   [一、zip 压缩包方式下载安装](#zip_38)
*   *   [1、下载 Redis 压缩包](#1Redis_40)
    *   [2、解压到文件夹](#2_50)
    *   [3、启动 Redis 服务](#3Redis_56)
    *   [4、打开 Redis 客户端进行连接](#4Redis_95)
    *   [5、使用一些基础操作来测试](#5_114)
*   [二、msi 安装包方式下载安装](#msi_144)
*   *   [1、下载 Redis 安装包](#1Redis_146)
    *   [2、进行安装](#2_160)
    *   [3、进行配置](#3_174)
    *   [4、启动服务](#4_191)
    *   [5、测试能否正常工作](#5_207)
*   [三、使用可视化工具](#_232)
*   *   [1、Redis Desktop Manager](#1Redis_Desktop_Manager_234)
    *   [2、RedisStudio](#2RedisStudio_248)
    *   [3、treeNMS](#3treeNMS_257)
*   [参考博文：](#_274)

> 文中介绍了 Windows 中 Redis 的安装包 mis 和压缩包 zip 的安装教程，还有几个 Redis 常用的可视化插件，如`treeNMS`、`RedisStudio`、`Redis Desktop Manager`等请选择性观看。

Redis 下载地址：
===========

**windows 版本 readis 下载（GitHub）：**

[https://github.com/tporadowski/redis/releases](https://github.com/tporadowski/redis/releases) **（推荐使用）**

[https://github.com/MicrosoftArchive/redis/releases](https://github.com/MicrosoftArchive/redis/releases)

**官网下载（无 Windows 版本）：** [https://redis.io/download](https://redis.io/download)

**Redis 中文网站：** [http://www.redis.cn](http://www.redis.cn)

所有版本这里都有：[https://download.redis.io/releases/](https://download.redis.io/releases/)（下载后是个 Linux 的压缩文件，需要下载、解压和编译）

**发行说明：**

[https://raw.githubusercontent.com/redis/redis/5.0/00-RELEASENOTES](https://raw.githubusercontent.com/redis/redis/5.0/00-RELEASENOTES)

> Redis 支持 32 位和 64 位。根据你所使用的系统和实际情况进行选择，这里我下载 **Redis-x64-xxx.zip** 压缩包到磁盘，解压后，将文件夹重新命名为 **redis**。

> Windows 下的`.msi`安装和`.zip`格式区别：
> 
> `.msi`是 Windows installer 开发出来的程序安装文件，它可以让你安装，修改，卸载你所安装的程序。说白了.[msi](https://so.csdn.net/so/search?q=msi&spm=1001.2101.3001.7020) 就是 Windows installer 的数据包，把所有和安装文件相关的内容封装在一个包里。此外：它还包含有关安装过程自己的信息。例如：安装序列、目标文件夹路径、安装选项和控制安装过程的属性。  
> `.zip`是一个压缩包，解压之后即可，不需要安装

一、zip 压缩包方式下载安装
===============

1、下载 Redis 压缩包
--------------

这里我在 GitHub 中下载 window 用的 5.0 版本`Redis-x64-5.0.14.1.zip`。

[https://github.com/tporadowski/redis/releases](https://github.com/tporadowski/redis/releases)

![](https://img-blog.csdnimg.cn/img_convert/10af1c0dfe7518318e4ae07621edbf7b.png)

![](https://img-blog.csdnimg.cn/img_convert/80fb20015a384165fb21080c65738751.png)

2、解压到文件夹
--------

将下载的压缩包解压到指定的文件夹中，如：**D:\Redis**，内容如下：

![](https://img-blog.csdnimg.cn/img_convert/7f930d382215f61d7e9f4d26767144da.png)

3、启动 Redis 服务
-------------

在 Redis 的安装目录下打开 cmd 窗口，然后执行命令来启动服务：

```
redis-server.exe redis.windows.conf

```

**切换到 redis 目录：**

> 可以打开 cmd 使用 cd 命令切换到 redis 所在的目录：`cd /d d:\redis`

![](https://img-blog.csdnimg.cn/img_convert/9fe540bb7d95a372fa3a5e47d9dc6b0f.png)  
直接在 Redis 目录路径处输入 cmd 回车也可以进入命令窗口  
![](https://img-blog.csdnimg.cn/img_convert/ac3999d3c2535a7225694c3120e938a6.png)

> **cd 切换目录命令示例：**
> 
> 例：cd // 显示当前目录
> 
> 例：cd … // 进入父目录
> 
> 例：cd /d d: // 进入上次 d 盘所在的目录（或在直接输入：d:）
> 
> 例：cd /d d:\ // 进入 d 盘根目录
> 
> 例：cd d: // 显示上次 d 盘所在的目录
> 
> 例：cd /d d:\src // 进入 d:\src 目录

随后使用`redis-server.exe redis.windows.conf`命令来启动 redis 服务：  
![](https://img-blog.csdnimg.cn/img_convert/8c8ebf59f638ab01ce77be0a41a25d1e.png)

> 默认端口为 6379，出现图上的图标说明 redis 服务启动成功。命令里面的 `redis.windows.conf` 可以省略，省略后，使用`redis-server.exe`命令会使用默认的配置。

为了方便，建议把 Redis 路径配置到系统变量 Path 值中，这样就省得再输路径了。  
![](https://img-blog.csdnimg.cn/img_convert/09a29e9f777a63958800e8033d50b2fe.png)

4、打开 [Redis 客户端](https://so.csdn.net/so/search?q=Redis%E5%AE%A2%E6%88%B7%E7%AB%AF&spm=1001.2101.3001.7020)进行连接
--------------------------------------------------------------------------------------------------------------

我们使用`redis-cli.exe`命令来打开 Redis 客户端：

```
redis-cli.exe -h 127.0.0.1 -p 6379

```

![](https://img-blog.csdnimg.cn/img_convert/5f11bd1117c3549657c19460d51282b8.png)  
在命令中输入 ping 命令来检测 redis 服务器与 redis 客户端的连通性，返回`PONG`则说明连接成功了。  
![](https://img-blog.csdnimg.cn/img_convert/cfa4cd2ec80c3aa623d3d06c2a75aa0a.png)  
如果出现连接不成功，注意服务打开以后，另启一个 cmd 窗口到 Redis 所在的目录执行命令，**原来的 Redis 启动窗口不要关闭**，不然就无法访问服务端了。  
![](https://img-blog.csdnimg.cn/img_convert/cfe24afd99d68e9fa59a2a6dd4f74443.png)

如果连接成功，到此 Redis 的安装和部署也就完成了。

5、使用一些基础操作来测试
-------------

**下面我们可以来进行一些基础操作来进行测试**

Redis 默认拥有 16 个数据库，初始默认使用 0 号库，在命令行中通过`select`命令将数据库切换到 8 号数据库：

```
select 8 

```

![](https://img-blog.csdnimg.cn/img_convert/248edb3809f099536c7945d2c4e4fa39.png)  
在命令中通过`set`命令设置键值，通过`get`命令取出键值：  
![](https://img-blog.csdnimg.cn/img_convert/6a32cdcc2445203d764d1568229b243c.png)  
在命令中通过`shutdown`命令来关闭 redis 服务：  
![](https://img-blog.csdnimg.cn/img_convert/09cc3752110886f250c9d1c574dfc088.png)  
在 Redis 服务启动的 cmd 窗口中会出现服务关闭的提醒，如下图：  
![](https://img-blog.csdnimg.cn/img_convert/f6242cd4cb27e0cd25df2976bd85d3f8.png)

**Redis 常用的服务指令**

卸载服务：`redis-server --service-uninstall`

开启服务：`redis-server --service-start`

停止服务：`redis-server --service-stop`

二、msi 安装包方式下载安装
===============

1、下载 Redis 安装包
--------------

这里我在 GitHub 中下载 window 用的 5.0 版本 Redis-x64-5.0.14.1.msi

这里选择. msi 格式的安装版本 (另外一种. zip 为本文中的第一种安装方式安装)

[https://github.com/tporadowski/redis/releases](https://github.com/tporadowski/redis/releases)

![](https://img-blog.csdnimg.cn/img_convert/5e734f2c1768088143dba7329113a9d0.png)

![](https://img-blog.csdnimg.cn/img_convert/7982e0b2d362f81e32ded2863cd48ebf.png)

2、进行安装
------

![](https://img-blog.csdnimg.cn/img_convert/21c0cd428b44d01c7f648e8f9dd947da.png)  
![](https://img-blog.csdnimg.cn/img_convert/46f163e2b46f30968a148cb0799a14c0.png)  
①直接运行`.msi`的安装包，一直 next，直到下面界面, 勾选上再 next  
![](https://img-blog.csdnimg.cn/img_convert/242ee0279896c4695c06bdcb9713fa1e.png)  
②这一步选择端口，然后 next（`默认6379`，后面可以通过配置文件修改的）  
![](https://img-blog.csdnimg.cn/img_convert/8aaf50a66d8164d730e7f69260a679b0.png)  
③选择最大缓存容量，点击 next（后面可以通过配置文件修改的）  
![](https://img-blog.csdnimg.cn/img_convert/ca4202e9e902cffd2faa8d9125a5f008.png)  
![](https://img-blog.csdnimg.cn/img_convert/c01b79be8a3f2b6021c757e466bc128d.png)  
接下来可以点击`install`进行安装了，如果安装有杀毒软件可以会权限提示，全部允许即可，不要点错了。  
![](https://img-blog.csdnimg.cn/img_convert/fadf78ac1f6ee2ba5d5a71feaf51ca90.png)  
![](https://img-blog.csdnimg.cn/img_convert/9e024ded125b21d306d2f6a5a16ef3d5.png)

3、进行配置
------

①安装完毕后，进入 redis 安装目录找到配置文件 **redis.windows-service.conf**

注意是 **redis.windows-service.conf** 不是 **redis.windows.conf**

后者是以非系统服务方式启动程序使用的配置文件.

![](https://img-blog.csdnimg.cn/img_convert/0bd1d8021f5667b6d276d1767a70a037.png)

②在配置文件中, 找到 **requirepass foobared** 字样，在其后面追加一行，输入`requirepass 123456`设置访问 Redis 时所需的密码。

一般测试情况下可以不用设定密码。我这里设置 123456 做演示。

![](https://img-blog.csdnimg.cn/img_convert/5d6b0a71070cb9a04682071179e2d9ff.png)

4、启动服务
------

进入计算机服务中 **(右键计算机 → 管理 → 服务和应用程序 → 服务)**

再在右侧找到 Redis 名称的服务，查看启动情况。

如未启动，则手动启动。

正常情况下，服务应该正常启动并运行了，**但是因为前面修改过配置文件，需要重启服务**

![](https://img-blog.csdnimg.cn/img_convert/4ae2bc347c911210955bbb4b6e04b3b0.png)

另外在【任务管理器】→【服务】中也可以启动

![](https://img-blog.csdnimg.cn/img_convert/1c8ff3885658fdbe1e3d33139c116985.png)

5、测试能否正常工作
----------

测试一下 redis 能否正常工作。

用命令进入 redis 安装路径

```
cd c:\redis

```

![](https://img-blog.csdnimg.cn/img_convert/2d1cde605be098aa174fe033b268eeca.png)  
输入`redis-cli`并回车（redis-cli 是客户端程序）如图正常提示进入，并显示正确端口号，则表示服务已经启动。

```
redis-cli

```

![](https://img-blog.csdnimg.cn/img_convert/41b28c26911074ea345ea5a5c3fe3a7e.png)  
由于刚刚配置了密码，使用服务前需要先通过密码验证。

输入 “`auth 123456`” 并回车（123456 是之前设定的密码）。

返回提示 OK 表示验证通过。  
![](https://img-blog.csdnimg.cn/img_convert/1d8b935a9121b1ef892f0bb586c27223.png)  
然后再验证 set 和 get 命令，如果一切正常便安装部署成功。  
![](https://img-blog.csdnimg.cn/img_convert/c09a7e271600c369eb3901ef6d5565b9.png)

三、使用可视化工具
=========

1、Redis Desktop Manager
-----------------------

需要安装使用，0.9.4 以上是要收费的

**下载地址：**[https://github.com/uglide/RedisDesktopManager/releases/download/0.9.3/redis-desktop-manager-0.9.3.817.exe](https://github.com/uglide/RedisDesktopManager/releases/download/0.9.3/redis-desktop-manager-0.9.3.817.exe)

**详情：**[https://blog.csdn.net/u012688704/article/details/82251338](https://blog.csdn.net/u012688704/article/details/82251338)

下载完成之后直接点击安装，无需任何配置直接连接。

![](https://img-blog.csdnimg.cn/img_convert/cb80fd3b65a5b818165975f4b921516f.png)  
界面如下：  
![](https://img-blog.csdnimg.cn/img_convert/0468fb35ece2920eb8248c10e13ada20.png)

2、RedisStudio
-------------

** 下载地址：**https://github.com/cinience/RedisStudio/releases

打开即可使用，  
![](https://img-blog.csdnimg.cn/img_convert/46ecd07bd03383a737d1dac60c24e6a7.png)  
界面如下：  
![](https://img-blog.csdnimg.cn/img_convert/91551e8e68eef67cea0a0a915e424bfd.png)

3、treeNMS
---------

treeNMS 管理工具

官网下载地址：http://www.treesoft.cn/dms.html

是用 JAVA 开发的，基于 WEB 方式对 Redis 管理，windows 环境下载解压即可使用，里面有部署说明

![](https://img-blog.csdnimg.cn/img_convert/6ceb46a473dcc7758f932dd0364efdaa.png)  
界面如下：  
![](https://img-blog.csdnimg.cn/img_convert/311e4d5a52b3fd0fb3415b7d6a1bb321.png)

![](https://img-blog.csdnimg.cn/img_convert/3694b88cf236f72e92997104323ce402.png)  
![](https://img-blog.csdnimg.cn/img_convert/bf72d721c9c1c9d2c38644d1c00a4ce9.png)

参考博文：
=====

CSDN@[脱毛的二哈](https://blog.csdn.net/qq_30211955)【windows 安装 Readis 与可视化工具】[https://blog.csdn.net/qq_30211955/article/details/88881361](https://blog.csdn.net/qq_30211955/article/details/88881361)

CSDN@[Zepal](https://blog.csdn.net/weixin_41381863)【windows 下 Redis 的安装和配置–图文教程】[https://blog.csdn.net/weixin_41381863/article/details/88231397](https://blog.csdn.net/weixin_41381863/article/details/88231397)

脚本之家 @一入码坑深似海 【推荐几款 Redis 可视化工具 (太厉害了)】[https://www.jb51.net/article/208969.htm](https://www.jb51.net/article/208969.htm)

![](https://img-blog.csdnimg.cn/img_convert/8fad59f402d8cdb0a5bac9dc2d29601d.png)