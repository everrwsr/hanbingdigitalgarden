---
{"dg-publish":true,"title":"关于JAVAweb环境配置的汇总 为刘某，许某，李某等朋友而作，主要是刘某，问某应该不需要,问某后来告诉我，她怎么不需要啦","permalink":"/03evermemo/02code/javaweb/01howtosetjavaweb-env-jav-aweb/","dgPassFrontmatter":true}
---


原文链接：
> https://www.yuque.com/u693751/woygo8/ph3dnks7zai9f94s
## 前言

> 因为最近很多人问，我不得不熟悉了一次次javaweb项目环境搭建和运行的全过程。
> 大多数人困惑和不习惯的点在于：
> javaweb项目对比过去所学的简单的C，C++，JAVA项目，
> 环境的搭建难度和复杂度上了一个台阶。
> 初步入门所谓的工程化编程领域，诸多不适和不习惯是正常的，
> 现代软件是大型合作工作，一个人写好所有的代码的时代远去了，你不得不使用其他人写的代码和框架，也就必须因此去理解和适应其他人的想法。这是痛苦的。
> 在初入javaweb世界中，
> 我曾有过这样无比困惑的阶段——
> - 那些反复安装就是不能运行的mysql,
> - 就是不能运行的tomcat,
> - 一直下载不下来的jar包，
> - 龟爬一样的maven下载包速度。
> - 在其他人电脑上能运行，就是我不能运行。
> - 。。。
> 
在此过程中：
> 网上csdn的教程质量有高有低，我曾被教程坑过，也幸得大佬提点。
> 我想汇总前辈优秀教程和我个人的一点浅见于此。
> 

> 前人走过的弯路，后人何必再走呢。
> 2022.12.16 于华州


---

<a name="H988U"></a>
## 计划

- [x] jdk安装和配置
- [x] idea旗舰版获取和使用
- [x] tomcat 配置和使用
- [x] maven相关
- [x] 如何运行其他人的javaweb项目
- [x] IDEA自带的数据库工具
- [x] navicat 教程
- [x] 如何修改网上其他人的项目图片
- [x] 常见问题 ✅ 2023-01-08

---

<a name="xvkMT"></a>
## 更新日志
> 2022.12.16 
> 为jdk都不晓得配置的刘某开始写了这篇教程
> 涵盖jdk,idea,tomcat , maven ,mysql等配置环境的东西。
> 2022.12.18   
> 文某看到原题目---关于JAVAweb环境配置的汇总------- 《为刘某，许某，李某等朋友而作，主要是刘某，问某应该不需要》，
> 经问某要求---(直言自己怎么不需要啦)，
> 故改名为------《关于JAVAweb环境配置的汇总 为刘某，许某，李某等朋友而作，主要是刘某，问某应该不需要,问某后来告诉我，她怎么不需要啦》
> 问开始错写为文，文某要揍我，我当然是义正严词告诉她----“我错了，呜呜”
> 不正经更新日志结束；
> 正经更新日志为：
> 添加idea自带数据库使用工具教程
> 添加navicat 安装和使用教程
> 添加修改项目小技巧，sql转word设计文档技巧
> 2011.12.20
> 添加更新修改项目小技巧，记得更改完成后开启浏览器无痕（隐私）模式，快捷键ctrl+shift+n（因为浏览器会默认缓存上一次的图片和其他资源文件，开无痕是强制不缓存罢了）
> 因为王某和一个刘某遇见了此问题，不得不更新下
> 还有刘某告诉我她很认真看了好几遍，我很感动，随意写就的部分，她的态度好好，故更新了一部分。
> 或许这个一开始随意起意的项目很值得发展哈哈


<a name="zgrpD"></a>
## 1.JDK 8


<a name="DvEiH"></a>
## 2. IDEA 和tomcat
有idea时，可以简单解压tomcat,不用太配置环境变量idea 会自动配置，非常好用！！！就可以直接使用tomcat教程如下：资源如下：[apache-tomcat-8.5.82.zip](https://www.yuque.com/attachments/yuque/0/2022/zip/906866/1671178474150-e09af694-0453-4cc9-8345-50c3f6c54007.zip?_lake_card=%7B%22src%22%3A%22https%3A%2F%2Fwww.yuque.com%2Fattachments%2Fyuque%2F0%2F2022%2Fzip%2F906866%2F1671178474150-e09af694-0453-4cc9-8345-50c3f6c54007.zip%22%2C%22name%22%3A%22apache-tomcat-8.5.82.zip%22%2C%22size%22%3A11849515%2C%22type%22%3A%22application%2Fx-zip-compressed%22%2C%22ext%22%3A%22zip%22%2C%22source%22%3A%22%22%2C%22status%22%3A%22done%22%2C%22mode%22%3A%22title%22%2C%22download%22%3Atrue%2C%22taskId%22%3A%22u7b3569a9-1b85-4b12-86af-46b1b901a9d%22%2C%22taskType%22%3A%22upload%22%2C%22__spacing%22%3A%22both%22%2C%22id%22%3A%22u15c30497%22%2C%22margin%22%3A%7B%22top%22%3Atrue%2C%22bottom%22%3Atrue%7D%2C%22card%22%3A%22file%22%7D)西安财经大学学生可以按照我写的这个教程获取正版IDEA，教育授权[IDEA 破解和正版路子](https://www.yuque.com/u693751/woygo8/gtg8ry)

---

<a name="yfk42"></a>
### 2.1 更换maven镜像为阿里云
如果项目存在pom.xml并且半天jar包下不下来那么按照下面的步骤进行[javaeb maven 镜像更换为阿里云镜像](https://www.yuque.com/u693751/woygo8/lhirszt4atrag2sv)

---

IDEA社区版下载需要安装smarttomcat插件
<a name="AHfkw"></a>
### 2.2 下载smartTomcat插件
![image.png](https://cdn.nlark.com/yuque/0/2022/png/906866/1671177237761-f4c7d7a3-d811-480b-9b15-da7da833e9b5.png#averageHue=%23d3ab67&clientId=u2fcb7f6f-bbd3-4&crop=0&crop=0&crop=1&crop=1&from=paste&id=ua8157f98&margin=%5Bobject%20Object%5D&name=image.png&originHeight=892&originWidth=1240&originalType=url&ratio=1&rotation=0&showTitle=false&size=118794&status=done&style=none&taskId=ua97f3760-8295-4f68-a701-089476977c7&title=)
<a name="TdxYK"></a>
### 2.3 smartTomcat的配置
![image.png](https://cdn.nlark.com/yuque/0/2022/png/906866/1671177237994-703a2875-9e24-4ed9-bb20-5ac3c557f0d5.png#averageHue=%23f6f3f2&clientId=u2fcb7f6f-bbd3-4&crop=0&crop=0&crop=1&crop=1&from=paste&id=u0b1ff077&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1029&originWidth=1920&originalType=url&ratio=1&rotation=0&showTitle=false&size=245720&status=done&style=none&taskId=u9dc82e96-1331-4944-bf31-1eb88e0c619&title=)![image.png](https://cdn.nlark.com/yuque/0/2022/png/906866/1671177237632-db16b84f-4b3d-462e-9176-34c146661270.png#averageHue=%23f3f2f2&clientId=u2fcb7f6f-bbd3-4&crop=0&crop=0&crop=1&crop=1&from=paste&id=u8191d992&margin=%5Bobject%20Object%5D&name=image.png&originHeight=847&originWidth=1322&originalType=url&ratio=1&rotation=0&showTitle=false&size=74189&status=done&style=none&taskId=u8ae8420a-87a4-4eef-9853-145a7d4ddb1&title=)这玩意要配置到WEB-INF才可以使用，
<a name="JDZ22"></a>
## 3. 数据库 
本人推荐MYSQL5.7安装新版本mysql前请务必确认成功**完全**卸载老版本mysql和残留文件和注册表信息。卸载教程

安装mysql 5.7 看这里[MYSQl5.7 安装教程](https://www.yuque.com/u693751/woygo8/eg2ly9t6xl29wi45)下载方式：

1. 官网下载
2. 我曾经一老师发过的凑合版本

[MySQL556_jb51.zip](https://www.yuque.com/attachments/yuque/0/2022/zip/906866/1671177461809-a3f2e03a-5f5a-422b-9198-a65ae128b827.zip?_lake_card=%7B%22src%22%3A%22https%3A%2F%2Fwww.yuque.com%2Fattachments%2Fyuque%2F0%2F2022%2Fzip%2F906866%2F1671177461809-a3f2e03a-5f5a-422b-9198-a65ae128b827.zip%22%2C%22name%22%3A%22MySQL556_jb51.zip%22%2C%22size%22%3A42114387%2C%22type%22%3A%22application%2Fx-zip-compressed%22%2C%22ext%22%3A%22zip%22%2C%22source%22%3A%22%22%2C%22status%22%3A%22done%22%2C%22mode%22%3A%22title%22%2C%22download%22%3Atrue%2C%22taskId%22%3A%22u44d2cf7c-1ab4-4e1f-aefd-7d40c40ed91%22%2C%22taskType%22%3A%22upload%22%2C%22__spacing%22%3A%22both%22%2C%22id%22%3A%22u7fc333a9%22%2C%22margin%22%3A%7B%22top%22%3Atrue%2C%22bottom%22%3Atrue%7D%2C%22card%22%3A%22file%22%7D)

3. 官网我下载的版本。

[mysql-5.7.24-winx64.zip](https://www.yuque.com/attachments/yuque/0/2022/zip/906866/1671177579150-85fe2bd9-a389-4127-b786-a3267e38d8da.zip?_lake_card=%7B%22src%22%3A%22https%3A%2F%2Fwww.yuque.com%2Fattachments%2Fyuque%2F0%2F2022%2Fzip%2F906866%2F1671177579150-85fe2bd9-a389-4127-b786-a3267e38d8da.zip%22%2C%22name%22%3A%22mysql-5.7.24-winx64.zip%22%2C%22size%22%3A336686815%2C%22type%22%3A%22application%2Fx-zip-compressed%22%2C%22ext%22%3A%22zip%22%2C%22source%22%3A%22%22%2C%22status%22%3A%22done%22%2C%22mode%22%3A%22title%22%2C%22download%22%3Atrue%2C%22taskId%22%3A%22ua29f57f9-5fd6-4786-9297-05c9d9908ff%22%2C%22taskType%22%3A%22upload%22%2C%22__spacing%22%3A%22both%22%2C%22id%22%3A%22ub579917c%22%2C%22margin%22%3A%7B%22top%22%3Atrue%2C%22bottom%22%3Atrue%7D%2C%22card%22%3A%22file%22%7D)

<a name="I7G7j"></a>
#### 3.1 navicat 教程
断开网络连接那一步可以通过修改host解决添加 127.0.0.1 activate.navicat.com 达到屏蔽Navicat激活联网

---

<a name="zjTBh"></a>
#### 3.2 idea 自带数据库
教程如下
<a name="setH7"></a>
## 4. 如何运行javaweb项目
怎么说呢，这是个很大的概念。总结下来大致步骤如下

1. 修改jdbc设置，数据库，用户名，密码，端口等
2. 导入sql文件
3. 配置项目结构，和Tomcat等服务器
4. 运行。

可以参考的文档：


<a name="eFLLa"></a>
#### 4.1 修改项目小技巧（更换图片和其他）：

1. 通过IDEA快捷键 Ctrl+Shift+r 或这点击 Edit 》Find 》Replace In Path,请活用哈哈，在网页上看到啥去项目里搜索替换
2. 修改网页背景图片，用同名文件替代或删除,记住更换后，点击重新运行

> ![image.png](https://cdn.nlark.com/yuque/0/2022/png/906866/1671513046964-62e7f35b-5258-4515-9cab-a4110ea45d5d.png#averageHue=%23414b4c&clientId=uc2c971fc-ad13-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=775&id=ub21a3a35&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1356&originWidth=857&originalType=binary&ratio=1&rotation=0&showTitle=false&size=613161&status=done&style=none&taskId=u484b1df8-4725-43d2-9973-ee8c195a587&title=&width=489.7142857142857)
> 2.![image.png](https://cdn.nlark.com/yuque/0/2022/png/906866/1671515346894-7c695b1c-25e2-4bc2-9c30-7f1ffde5999c.png#averageHue=%23323533&clientId=uc2c971fc-ad13-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=520&id=u559b2b5b&margin=%5Bobject%20Object%5D&name=image.png&originHeight=910&originWidth=1484&originalType=binary&ratio=1&rotation=0&showTitle=false&size=909793&status=done&style=none&taskId=u15265608-c197-4e46-9fcd-dbe68ca98a5&title=&width=848)

3. 并且使用浏览器无痕模式打开项目
4. 快捷键ctrl+shift+n

5. 
<a name="WCldR"></a>
#### 4.2 修改数据库小技巧：
不要直接删除数据库记录要尽量直接修改，不然数据库设计者的大量关联项目会被你删掉

<a name="gX7D2"></a>
#### 4.3 sql语句转 word数据库设计文档方法

[[03evermemo/02code/javaweb/14 how to sql转word,html ,pdf method 1\|14 how to sql转word,html ,pdf method 1]]




