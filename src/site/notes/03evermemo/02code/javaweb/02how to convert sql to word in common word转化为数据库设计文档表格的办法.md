---
{"dg-publish":true,"permalink":"/03evermemo/02code/javaweb/02how to convert sql to word in common word转化为数据库设计文档表格的办法/","dgPassFrontmatter":true,"noteIcon":"","created":"","updated":""}
---



#javaweb 
#sql
#word
#数据库 






navicat 选中要导出的数据库
## 写在前面

这里记录下，从数据库表结构，同步到数据库文档设计Word文档

我们需要的文档信息，大致如下

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200325130024804.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQyMTA1NjI5,size_16,color_FFFFFF,t_70)

## 一、基本环境

Navicate + Java 环境（从Excel转Word）

## 二、准备数据

```sql
SELECT
    TABLE_NAME Tables,
    COLUMN_NAME 字段,
    COLUMN_COMMENT 名称,
    COLUMN_TYPE 类型,
    'false' as 是否必须,
    COLUMN_COMMENT 注释、描述
FROM
    INFORMATION_SCHEMA.COLUMNS
where table_schema = '数据库名';
```

将检索数据，导出如下，这里我导出的.xlsx格式（因为很多丰富的类库选择解析Excel）

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200325130453553.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQyMTA1NjI5,size_16,color_FFFFFF,t_70)  
导出的Excel,合并列后  
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200325140301343.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQyMTA1NjI5,size_16,color_FFFFFF,t_70)  
如果想转成 Word,可参考，待写

[[03evermemo/02code/javaweb/14 how to sql转word,html ,pdf method 1\|14 how to sql转word,html ,pdf method 1]]
