---
{"url":"https://blog.csdn.net/ic_xcc/article/details/121425926","title":"(5 条消息) CentOS7 下安装 mysql5.7（亲测完成）_ic_xcc 的博客 - CSDN 博客","date":"2023-04-02 11:38:03","tag":null,"summary":null,"dg-publish":true,"permalink":"/webpage/CentOS7 下安装 mysql5_7（亲测完成）_ic_xcc 的博客 - CSDN 博客/","dgPassFrontmatter":true}
---

### [CentOS7](https://so.csdn.net/so/search?q=CentOS7&spm=1001.2101.3001.7020) 下安装 mysql5.7

*   [前言](#_1)
*   [一、环境地址新建、清除旧安装包](#_3)
*   [二、安装 YUM](#YUM_33)
*   [三、使用 yum 命令即可完成安装](#yum_48)
*   *   [问题一：如果遇到安装不成功，提示：The GPG keys listed for the "MySQL 5.7 Community Server" repository are already installed but they are not correct for this package.](#The_GPG_keys_listed_for_the_MySQL_57_Community_Server_repository_are_already_installed_but_they_are_not_correct_for_this_package_55)
    *   [解决：yum 添加 --nogpgcheck](#yumnogpgcheck_59)
    *   *   [原因](#_60)
        *   [办法](#_62)
    *   [问题二：登录报错 ERROR 1045](#ERROR_1045_85)
    *   [解决：修改 my.cnf 文件](#mycnf_88)
    *   [问题三：登录报错 ERROR 1820 You must reset your password using ALTER USER statement before executing this statement.](#ERROR_1820_You_must_reset_your_password_using_ALTER_USER_statement_before_executing_this_statement_113)
    *   [解决：重新设置密码](#_116)
*   [四、navicat 测试连接成功](#navicat_177)
*   [五、参考文章](#_181)

# 前言

近期项目需要配合 mysql 一起记录相关数据，于是在服务器搭建了 mysql，顺便记录一下搭建步骤和踩坑解决步骤

# 一、环境地址新建、清除旧安装包

1.  进入到目录 /usr/local/ 中

```
cd /usr/local/

```

2.  创建目录 /usr/local/tools，如果有则忽略

```
mkdir -p tools

```

3.  创建 /usr/local/mysql 目录，如果已存在则忽略

```
mkdir -p mysql

```

4.  进入到目录 /usr/local/tools 中

```
cd tools/

```

5.  查看系统中是否已安装 MySQL 服务

```
rpm -qa | grep mysql
或
yum list installed | grep mysql

```

6.  如果已安装则删除 MySQL 及其依赖的包

```
yum -y remove mysql-libs.x86_64

```

![](https://img-blog.csdnimg.cn/d2ee5ed7ea184ed198d02e7257fe4e35.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAaWNfeGNj,size_20,color_FFFFFF,t_70,g_se,x_16)

# 二、安装 YUM

1.  下载 mysql57-community-release-el7-8.noarch.rpm 的 YUM 源  
    下载命令：

```
wget http://repo.mysql.com/mysql57-community-release-el7-8.noarch.rpm

```

2.  然后进行 repo 的安装：

```
rpm -ivh mysql57-community-release-el7-8.noarch.rpm

```

![](https://img-blog.csdnimg.cn/12de84f5a9f442918b2b7d20c0158656.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAaWNfeGNj,size_20,color_FFFFFF,t_70,g_se,x_16)

  
执行完成后会在 / etc/yum.repos.d / 目录下生成两个 repo 包：  
mysql-community.repo  
mysql-community-source.repo  

![](https://img-blog.csdnimg.cn/add5e050b80a45faa1354db1b83e7a30.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAaWNfeGNj,size_20,color_FFFFFF,t_70,g_se,x_16)

# 三、使用 yum 命令即可完成安装

注意：必须进入到 /etc/yum.repos.d / 目录后再执行以下脚本

1.  安装命令：

```
yum install mysql-server

```

## 问题一：如果遇到安装不成功，提示：The GPG keys listed for the “MySQL 5.7 Community Server” repository are already installed but they are not correct for this package.

Check that the correct key URLs are configured for this repository.  

![](https://img-blog.csdnimg.cn/f1d9ed5d110e45e899f1dbfa1f721425.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAaWNfeGNj,size_20,color_FFFFFF,t_70,g_se,x_16)

## 解决：yum 添加–nogpgcheck

### 原因

软件开发商在释出 RPM 文件时，会在其中添加数字签名，并释出用于验证数字签名的公钥。使用 rpm 安装软件时，rpm 会首先根据系统中已有的公钥去验证 RPM 文件的数字签名。gpg keys 就是公钥。

### 办法

yum 安装的时候就会校验软件包是否是官方发布的。当然可以给 yum 添加–nogpgcheck 来强制安装，如下命令即可

```
yum install mysql-server --nogpgcheck

```

所以在安装的时候会比对已有的公钥，发现不正确，报错了  
2. 启动 msyql：

```
systemctl start mysqld #启动MySQL

```

3.  获取安装时的临时密码（在第一次登录时就是用这个密码）：

```
grep 'temporary password' /var/log/mysqld.log

```

![](https://img-blog.csdnimg.cn/90bf4fae420d4f22a573ede8b214c983.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAaWNfeGNj,size_20,color_FFFFFF,t_70,g_se,x_16)

4.  登录 mysql

```
mysql -u root -p

然后输入密码（刚刚获取的临时密码）

```

## 问题二：登录报错 ERROR 1045

倘若获取临时密码，登录报错 ERROR 1045 (28000): Access denied for user ‘root’@‘localhost’ (using password: YES)  

![](https://img-blog.csdnimg.cn/7a5530b4a95448939573dad054733928.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAaWNfeGNj,size_20,color_FFFFFF,t_70,g_se,x_16)

## 解决：修改 my.cnf 文件

1.  首先，停止 MySQL 服务

```
service mysqld stop

```

2.  既然是密码错误，那么就先跳过密码验证的步骤，打开 my.cnf 文件，更改不启动授权表

```
vim /etc/my.cnf

```

![](https://img-blog.csdnimg.cn/ca9bfa286fe44fe9b2d55c36c4091ad5.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAaWNfeGNj,size_20,color_FFFFFF,t_70,g_se,x_16)

然后，搜索 mysqld，找到 [mysqld]，在最后加上添加一行语句：

/mysqld(在 vim 编辑状态下直接输入该命令可搜索文本内容)。

注：windows 下修改的是 my.ini。

在 [mysqld] 底下添加语句：

```
skip-grant-tables

```

（注：skip-grant-tables：不启动 grant-tables 授权表，作为启动参数的作用：MYSQL 服务器不加载权限判断，任何用户都能访问数据库）

这是用来跳过密码验证的，添加之后保存退出。  

![](https://img-blog.csdnimg.cn/4db4942412264a4f905b4656cdf92a19.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAaWNfeGNj,size_20,color_FFFFFF,t_70,g_se,x_16)

## 问题三：登录报错 ERROR 1820 You must reset your password using ALTER USER statement before executing this statement.

输入上面得到的密码进入，用该密码登录后，必须马上修改新的密码，不然会报如上述错误：  

![](https://img-blog.csdnimg.cn/6665ef56ee574a7cb4a7218f681200f5.png)

## 解决：重新设置密码

如果你想要设置一个简单的测试密码的话，比如设置为 123456，会提示这个错误，报错的意思就是你的密码不符合要求：  
ERROR 1819 (HY000): Your password does not satisfy the current policy requirements  
这个其实与 validate_password_policy 的值有关。  
validate_password_policy 有以下取值：  

![](https://img-blog.csdnimg.cn/ca44273aa0c94fa7957aa7e4129e1b7c.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAaWNfeGNj,size_20,color_FFFFFF,t_70,g_se,x_16)

  
默认是 1，即 MEDIUM，所以刚开始设置的密码必须符合长度，且必须含有数字，小写或大写字母，特殊字符。  
有时候，只是为了自己测试，不想密码设置得那么复杂，譬如说，我只想设置 root 的密码为 123456。  
必须修改两个全局参数：

1.  首先，修改 validate_password_policy 参数的值

```
mysql> set global validate_password_policy=0;
Query OK, 0 rows affected (0.00 sec)

```

2.  validate_password_length(密码长度) 参数默认为 8，我们修改为 1

```
mysql> set global validate_password_length=1;
Query OK, 0 rows affected (0.00 sec)

```

3.  完成之后再次执行修改密码语句即可成功

```
mysql> alter user 'root'@'localhost' identified by '654321';
Query OK, 0 rows affected (0.00 sec)

```

![](https://img-blog.csdnimg.cn/5aabecfd036843df890523fdf39716f2.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAaWNfeGNj,size_20,color_FFFFFF,t_70,g_se,x_16)

3.  重新启动 MySQL 服务

```
systemctl start mysqld #启动MySQL

```

4.  进入 MySQL  
    出现密码输入时，不用输入直接按回车，就可以不用密码就能登录

```
mysql -u root -p
密码直接回车

```

![](https://img-blog.csdnimg.cn/53275893e24b4d2b8a73dfd6ad9a4245.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAaWNfeGNj,size_20,color_FFFFFF,t_70,g_se,x_16)

5.  mysql 连接成功，修改密码

*   5.1、看当前所有数据库：show databases;
    
*   5.2、进入 mysql 数据库：use mysql;
    
*   5.3、查看 mysql 数据库中所有的表：show tables;  
    
    ![](https://img-blog.csdnimg.cn/68bc15964f094063b31c4bef5099c0cd.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAaWNfeGNj,size_20,color_FFFFFF,t_70,g_se,x_16)
    
*   5.4、查看 user 表下的角色和密码，  
    注意：5.7 版本下的 mysql 数据库下已经没有 password 这个字段了，password 字段改成了 authentication_string
    

```
 select Host,User,authentication_string from user;

```

说明： % 代表任意的客户端, 可替换成具体 IP 地址。  

![](https://img-blog.csdnimg.cn/b87e4aed805141c58707b85d1b0bd406.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAaWNfeGNj,size_20,color_FFFFFF,t_70,g_se,x_16)

*   5.5、修改密码

```
update user set authentication_string=password(“新密码”) where user=”用户名”;

```

![](https://img-blog.csdnimg.cn/a8dd614a21db48a1a814afbd659be5e5.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAaWNfeGNj,size_20,color_FFFFFF,t_70,g_se,x_16)

  
密码修改完毕

# 四、[navicat](https://so.csdn.net/so/search?q=navicat&spm=1001.2101.3001.7020) 测试连接成功

*   打开 navicat 配置服务器的主机、端口、用户名、密码（刚刚修改过的）测试链接成功  
    
    ![](https://img-blog.csdnimg.cn/34914704b6e24155aa8eb61cb352fed3.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAaWNfeGNj,size_20,color_FFFFFF,t_70,g_se,x_16)
    

# 五、参考文章

[CentOS7 下安装 mysql5.7](https://blog.csdn.net/wohiusdashi/article/details/89358071)  
[在 CentOS7 上安装 MySQL5.7](https://www.linuxidc.com/Linux/2016-06/132676.htm)  
[MySQL1045 错误解决方法](https://my.oschina.net/u/4393165/blog/4613449)