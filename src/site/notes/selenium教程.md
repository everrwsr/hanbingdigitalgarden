---
{"dg-publish":true,"permalink":"/selenium教程/","dgPassFrontmatter":true}
---

> 鉴于发现问某人这个大好人环境部署有点小问题，故写了一个简单的环境部署和检查教程
> 使用教程来自网上


## 环境准备

### python环境

- 首先确保安装python3.7及以上版本，以便selenium使用，版本太低会出现不兼容现象

- 安装selenium包，目前主流版本是selenium3,但最新版本是selenium4,新版本不兼容老版本，需注意
```
pip install  selenium==3
```


如果报错，pip不是可以识别的程序，那么就是python安装的时候没有设置好环境变量
参考这个教程设置好环境变量
[python手动添加环境变量（超详细）（只适用win11/win10/win8，win7用户请绕行）\_python添加环境变量\_梦醒孤漠吃花卷的博客-CSDN博客](https://blog.csdn.net/l15668952150/article/details/124571667)


>[!TIP]
>设置完环境变量后必须关闭那个设置环境变量的几个窗口，然后新开一个cmd,环境变量的刷新才可以完成




同时设置完环境变量后在cmd执行下面的代码，加速python下载包速度
```
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple

```



## 驱动环境

#### 安装办法1 自己手动下载对应版本driver

教程如下

[Selenium+WebDriver 各浏览器驱动下载与使用\_webdriver下载\_番茄jason的博客-CSDN博客](https://blog.csdn.net/kenny_pj/article/details/103646745)

#### 安装办法2 通过webdriver manager 自动下载驱动

首先安装webdriver manager 这个第三方库
在cmd或者powershell运行下面的代码
```
pip install webdriver-manager
```

之后新建一个python文件
复制以下代码
```
#selenium 3 版本
from selenium import webdriver
from webdriver_manager.chrome import ChromeDriverManager

# 加载驱动和下载驱动
driver = webdriver.Chrome(ChromeDriverManager().install())

# 打开链接
driver.get("https://www.baidu.com/")


```


## 开始使用
教程如下;
[selenium入门超详细教程——网页自动化操作\_selenium入门教程\_Yunlord的博客-CSDN博客](https://blog.csdn.net/kobepaul123/article/details/128796839)
