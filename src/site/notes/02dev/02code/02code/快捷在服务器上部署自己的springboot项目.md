---
{"dg-publish":true,"permalink":"/02dev/02code/02code/快捷在服务器上部署自己的springboot项目/","dgPassFrontmatter":true}
---

# 快捷在服务器上部署自己的springboot项目

防火墙一定要放行

一定要把腾讯云的防火墙和宝塔的同时放行，不能忘记任意一个

所有需要外网访问的都必须开这个

## 安装宝塔

yum install -y wget && wget -O install.sh https://download.bt.cn/install/install_6.0.sh && sh install.sh 12f2c1d72

[宝塔Linux面板安装教程 - 2023年5月11日更新 - 7.9.10正式版 - Linux面板 - 宝塔面板论坛 (bt.cn)](https://www.bt.cn/bbs/thread-19376-1-1.html)

## 配置基本环境

Jdk  安装教程

1、检索检索1.8的列表

yum list java-1.8*

2、安装1.8.0的所有文件

yum install java-1.8.0-openjdk* -y

3、使用命令检查是否安装成功

java -version

Mysql

宝塔默认会安装，你到时候选个mysql8就行

## 开始部署

教程如下

https://www.bt.cn/bbs/thread-76217-1-1.html