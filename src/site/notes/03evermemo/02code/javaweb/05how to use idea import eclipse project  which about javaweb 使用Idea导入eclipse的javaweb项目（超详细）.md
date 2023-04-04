---
{"dg-publish":true,"permalink":"/03evermemo/02code/javaweb/05how to use idea import eclipse project  which about javaweb 使用Idea导入eclipse的javaweb项目（超详细）/","dgPassFrontmatter":true}
---

#idea
#javaweb 
#eclipse
#tutorial


https://blog.csdn.net/qq_42076902/article/details/123841422
## B站视频步骤

[点此](https://www.bilibili.com/video/BV1di4y1D7U4?spm_id_from=333.999.0.0)

1.首先选择打开该项目


<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">





</div></div>
(https://img-blog.csdnimg.cn/5ff0b9c747cc47f69367d48c42f76793.png)

2.打开后会是这样的，只显示.classpath和.project的[eclipse](https://so.csdn.net/so/search?q=eclipse&spm=1001.2101.3001.7020)文件  
![在这里插入图片描述](https://img-blog.csdnimg.cn/946c3b53ddbd4b4593d3cd7d04ab5f52.png)

3.打开project structre  
![在这里插入图片描述](https://img-blog.csdnimg.cn/7fc625b5284f411d8d28adaa57a8a35e.png)

4.在project structre中点击modules，然后点击+号，选import module，选择该文件夹的位置

![[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-1Fm5fXqf-1648609655272)(image-20220330103139585.png)\|外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-1Fm5fXqf-1648609655272)(image-20220330103139585.png)]](https://img-blog.csdnimg.cn/a3b5ec2ac53944cbae2f9800eee4172d.png)

![在这里插入图片描述](https://img-blog.csdnimg.cn/3bee81d71a5c4057a2fe88bc5949252a.png)

5.选择eclipse，点击next

![[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-pBGSAQDv-1648609655276)(image-20220330103348223.png)\|外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-pBGSAQDv-1648609655276)(image-20220330103348223.png)]](https://img-blog.csdnimg.cn/e2a4c4f7ec1c406f8a0b9d61f339d7c0.png)

6.选择keep project and module files in，然后继续点击next

![[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-VL1lpmqp-1648609655278)(image-20220330103425986.png)\|外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-VL1lpmqp-1648609655278)(image-20220330103425986.png)]](https://img-blog.csdnimg.cn/fea527fe5e5541c390512e1cbb9ed0f9.png)

7.选中项目名，点击next  
![在这里插入图片描述](https://img-blog.csdnimg.cn/0363771e6f4042c8b9594206f91a47fe.png)

8.点击finish，然后点yes  
![在这里插入图片描述](https://img-blog.csdnimg.cn/72ab3a5a21954258a32b4202678ca5b6.png)

![在这里插入图片描述](https://img-blog.csdnimg.cn/8d3f173304844dafbb139d0a56a7d457.png)

9.删除报红的选项（选中，然后点击-号）  
![在这里插入图片描述](https://img-blog.csdnimg.cn/baaf8954aa234cc98569f66268f77223.png)

10.添加lib，点击project structre中的libraries点击+选中Java，然后选择项目中的lib文件夹，一般都是在web或者webcontent中WEB-INF文件夹里边。  
![在这里插入图片描述](https://img-blog.csdnimg.cn/b3e7375b082341838b59d81d74106dbb.png)

![[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-yMGh2hbi-1648609655292)(image-20220330103956762.png)\|外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-yMGh2hbi-1648609655292)(image-20220330103956762.png)]](https://img-blog.csdnimg.cn/17164324610349eca177c1779ce0e07d.png)

11.在Modules中的Dependecies添加刚刚添加的lib，然后添加tomcat服务器，出去后记得选中lib和Tomcat如下边第三个图

![[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-BOiu5yAB-1648609655295)(image-20220330104119481.png)\|外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-BOiu5yAB-1648609655295)(image-20220330104119481.png)]](https://img-blog.csdnimg.cn/a828ff95558f45e8b6d8023edca841ac.png)

![在这里插入图片描述](https://img-blog.csdnimg.cn/085b559a778b4d4390acaae8ab711193.png)

![[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-AwweCZvY-1648609655297)(image-20220330104222718.png)\|外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-AwweCZvY-1648609655297)(image-20220330104222718.png)]](https://img-blog.csdnimg.cn/b0f808abd617402596dc69076e3ffc9c.png)

12.在Facets中添加Web

![[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-XFJpFXGg-1648609655300)(image-20220330104320141.png)\|外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-XFJpFXGg-1648609655300)(image-20220330104320141.png)]](https://img-blog.csdnimg.cn/e604ff4116144f02ba6650bb0a63c3d6.png)

13.把已拥有的两个全部删掉，如删除下图已经圈中的

![[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-uC5sA44C-1648609655302)(image-20220330104454562.png)\|外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-uC5sA44C-1648609655302)(image-20220330104454562.png)]](https://img-blog.csdnimg.cn/3df8f2e9306b405798b4a81c2bae0687.png)

14.添加项目中的web.xml文件和存放Web的文件夹，一般web.xml在项目名\WebContent\WEB-INF\web.xml，存放web的文件夹一般都是在webcontent或者web文件夹中

![[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-upw18C0x-1648609655304)(image-20220330104945370.png)\|外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-upw18C0x-1648609655304)(image-20220330104945370.png)]](https://img-blog.csdnimg.cn/712efbef4245452ab783f5808f6f2636.png)

![[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-gaXX7uOO-1648609655306)(image-20220330105013007.png)\|外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-gaXX7uOO-1648609655306)(image-20220330105013007.png)]](https://img-blog.csdnimg.cn/fa64419c3e9a4b6490ebd41ebf1d088e.png)

15.点击artifacts，点+号，然后选中web application exploded 然后选中from modules，选中刚刚的项目

![[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-yjrdXVo7-1648609655307)(image-20220330105104561.png)\|外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-yjrdXVo7-1648609655307)(image-20220330105104561.png)]](https://img-blog.csdnimg.cn/8b4ef327081445909d14c57f63897636.png)

![[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-77VzHgkN-1648609655310)(image-20220330105249115.png)\|外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-77VzHgkN-1648609655310)(image-20220330105249115.png)]](https://img-blog.csdnimg.cn/45508640b76447bd9d9dcbab3c52cd2e.png)

16.先点击apply，再点击ok

![[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-4C4Q3aEi-1648609655311)(image-20220330105306035.png)\|外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-4C4Q3aEi-1648609655311)(image-20220330105306035.png)]](https://img-blog.csdnimg.cn/6b790f3121af4260b8eacb7af36afab1.png)  
17.在数据库中建表，首先找到项目中过的applicationContext.xml文件或者druid.properties配置中，根据表名建表和修改数据库登录验证信息

![[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-DJDpCXPm-1648621501140)(image-20220330141928310.png)\|外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-DJDpCXPm-1648621501140)(image-20220330141928310.png)]](https://img-blog.csdnimg.cn/08ba0275da834053b2482b5b8ac2997c.png)

18.打开navicat，创建相关的库名，鼠标放到相应的库名，右键点击运行SQL文件，然后找到.sql文件，导入数据库，刷新查看到导入结果

![[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-suS7qWo8-1648621501143)(image-20220330142250091.png)\|外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-suS7qWo8-1648621501143)(image-20220330142250091.png)]](https://img-blog.csdnimg.cn/e5cffef592d2408094b04bec16651ef7.png)

![在这里插入图片描述](https://img-blog.csdnimg.cn/49bac3d42af142569b69437794a63397.png)

19.最后就是将项目部署在tomcat上

![[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-x1QD0PHc-1648609655313)(image-20220330105535400.png)\|外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-x1QD0PHc-1648609655313)(image-20220330105535400.png)]](https://img-blog.csdnimg.cn/d4ce77da9be14a329570391cedc424c0.png)

点击deployment添加artifact，选中刚刚的项目

![[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-tr6a6bMU-1648609655316)(image-20220330105555037.png)\|外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-tr6a6bMU-1648609655316)(image-20220330105555037.png)]](https://img-blog.csdnimg.cn/533f5982e9f04bb696f54ffb360a09f1.png)

20.将application context改为/项目名

![[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-BxjXY8Dh-1648609655317)(image-20220330105649021.png)\|外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-BxjXY8Dh-1648609655317)(image-20220330105649021.png)]](https://img-blog.csdnimg.cn/dfd93d0ac4bb44358741d1abfbbffcea.png)

21.然后点击server，其他配置按照下图设置即可

![[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-wCBHFvQv-1648609655321)(image-20220330105801151.png)\|外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-wCBHFvQv-1648609655321)(image-20220330105801151.png)]](https://img-blog.csdnimg.cn/e1ae16e0ffb04cacb08d3db075636d71.png)

22.最后就是启动项目了，点击右上角绿色的小图标

![[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-VK1tEV6z-1648609655323)(image-20220330105949159.png)\|外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-VK1tEV6z-1648609655323)(image-20220330105949159.png)]](https://img-blog.csdnimg.cn/4f1e49979e6c4f579108685b12d57fa5.png)

23.这样服务就启动起来了

![[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-FWWAWm0q-1648609655324)(image-20220330110017481.png)\|外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-FWWAWm0q-1648609655324)(image-20220330110017481.png)]](https://img-blog.csdnimg.cn/7fa70a55dd304d3b8756112cbbdd2992.png)

## 其他注意事项

如果在启动Tomcat服务器的时候遇到1099号端口被占用（下图）

![[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-mrgwVVcY-1648609655326)(image-20220330110345262.png)\|外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-mrgwVVcY-1648609655326)(image-20220330110345262.png)]](https://img-blog.csdnimg.cn/4a923a71ee5148f2893852902863f765.png)

解决步骤：

1.win+r打开输入cmd打开黑窗口

2.输入**netstat -aon|findstr 1099**找到占用端口的进程

![在这里插入图片描述](https://img-blog.csdnimg.cn/01bec8d7ed9d4f9f8e5873ea4d8632c0.png)

3.taskkill -f -pid 16988（进程号）

这样就可以正常启动Tomcat了.