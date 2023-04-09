---
{"dg-publish":true,"permalink":"/Python自动化测试/","dgPassFrontmatter":true}
---


## Selenium设置

新版可以直接使用driver manager自动下载驱动，不用自己去查阅版本号对应关系并设置
环境变量
[[webpage/安装浏览器驱动 _ Selenium\|安装浏览器驱动 _ Selenium]]


```
pip install webdriver-manager
```

测试代码两个版本的selenium


```
# selenium 3
from selenium import webdriver
from webdriver_manager.chrome import ChromeDriverManager

driver = webdriver.Chrome(ChromeDriverManager().install())
```

```
# selenium 4
from selenium import webdriver
from selenium.webdriver.chrome.service import Service as ChromeService
from webdriver_manager.chrome import ChromeDriverManager

driver = webdriver.Chrome(service=ChromeService(ChromeDriverManager().install()))
```
