---
{"dg-publish":true,"permalink":"/01inbox/windows 常用命令/","dgPassFrontmatter":true,"noteIcon":"","created":"","updated":""}
---





## 1. 端口被占用

```
netstat -ano | findstr 8080
taskkill /pid    进程号   /f
```


