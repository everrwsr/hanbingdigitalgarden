---
{"dg-publish":true,"permalink":"/03evermemo/02code/javaweb/12 how to set idea maven设置/","dgPassFrontmatter":true,"noteIcon":"","created":"","updated":""}
---

选中项目pom.xml文件，右键选择打开settings.xml配置
[[03evermemo/02code/javaweb/09java web 's knowledge 的一些目录含义\|09java web 's knowledge 的一些目录含义]]
详情见下面的总和文章

[[03evermemo/02code/javaweb/01howtosetjavaweb env关于JAVAweb环境配置的汇总 为刘某，许某，李某等朋友而作，主要是刘某，问某应该不需要,问某后来告诉我，她怎么不需要啦\|01howtosetjavaweb env关于JAVAweb环境配置的汇总 为刘某，许某，李某等朋友而作，主要是刘某，问某应该不需要,问某后来告诉我，她怎么不需要啦]]

#javaweb 
#maven
	
```xml
<?xml version="1.0" encoding="UTF-8"?>  
<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"  
        xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0 http://maven.apache.org/xsd/settings-1.0.0.xsd">  
  
   <!-- 本地仓库的位置 -->  
   <localRepository>${user.home}/.m2/repository</localRepository>  
  
   <!-- Apache Maven 配置 -->  
   <pluginGroups/>  
   <proxies/>  
  
   <!-- 私服发布的用户名密码 -->  
   <servers>  
  
   </servers>  
  
   <!-- 阿里云镜像 -->  
   <mirrors>  
      <mirror>  
         <id>alimaven</id>  
         <name>aliyun maven</name>  
         <!-- https://maven.aliyun.com/repository/public/ -->  
         <url>https://maven.aliyun.com/nexus/content/groups/public/</url>  
         <mirrorOf>central</mirrorOf>  
      </mirror>  
   </mirrors>  
  
   <!-- 配置: java8, 先从阿里云下载, 没有再去私服下载  -->  
   <!-- 20190929 hepengju 测试结果: 影响下载顺序的是profiles标签的配置顺序(后面配置的ali仓库先下载), 而不是activeProfiles的顺序 -->  
   <profiles>  
      <!-- 全局JDK1.8配置 -->  
      <profile>  
         <id>jdk1.8</id>  
         <activation>  
            <activeByDefault>true</activeByDefault>  
            <jdk>1.8</jdk>  
         </activation>  
         <properties>  
            <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>  
            <maven.compiler.source>1.8</maven.compiler.source>  
            <maven.compiler.target>1.8</maven.compiler.target>  
            <maven.compiler.compilerVersion>1.8</maven.compiler.compilerVersion>  
         </properties>  
      </profile>  
  
  
      <!-- Nexus私服配置: 第三方jar包下载, 比如oracle的jdbc驱动等 -->  
  
  
      <!-- 阿里云配置: 提高国内的jar包下载速度 -->  
      <profile>  
         <id>ali</id>  
         <repositories>  
            <repository>  
               <id>alimaven</id>  
               <name>aliyun maven</name>  
               <url>https://maven.aliyun.com/nexus/content/groups/public/</url>  
               <releases>  
                  <enabled>true</enabled>  
               </releases>  
               <snapshots>  
                  <enabled>true</enabled>  
               </snapshots>  
            </repository>  
         </repositories>  
         <pluginRepositories>  
            <pluginRepository>  
               <id>alimaven</id>  
               <name>aliyun maven</name>  
               <url>https://maven.aliyun.com/nexus/content/groups/public/</url>  
            </pluginRepository>  
         </pluginRepositories>  
      </profile>  
  
   </profiles>  
  
   <!-- 激活配置 -->  
   <activeProfiles>  
      <activeProfile>jdk1.8</activeProfile>  
      <activeProfile>dev</activeProfile>  
      <activeProfile>ali</activeProfile>  
   </activeProfiles>  
</settings>
```