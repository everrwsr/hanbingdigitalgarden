---
{"dg-publish":true,"permalink":"/03evermemo/记录吴学姐遇到的win11系统文件夹异常解决方法/","dgPassFrontmatter":true}
---


参考教程

[[webpage/系统文件夹的位置异常 - Microsoft Community\|系统文件夹的位置异常 - Microsoft Community]]


链接如下
[系统文件夹的位置异常 - Microsoft Community](https://answers.microsoft.com/zh-hans/windows/forum/all/%E7%B3%BB%E7%BB%9F%E6%96%87%E4%BB%B6%E5%A4%B9/aefbf6b3-72f3-4518-a34e-c6776666a55e)

个人采用方法，查找win11注册表里
```
计算机\HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\User Shell Folders

该项所有的注册表值，
让其与默认相符合即可

默认值可从网上复制粘贴，
也可找一台正常的电脑进行查看所有值，进行复制粘贴即可



```
