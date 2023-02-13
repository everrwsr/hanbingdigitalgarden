---
{"dg-publish":true,"permalink":"/03evermemo/02code/javaweb/page-context-request-context-path/","dgPassFrontmatter":true}
---



- 
-   ${pageContext.request.contextPath}是JSP取得绝对路径的方法，等价于<%=request.getContextPath()%> 。
    
    也就是取出部署的应用程序名或者是当前的项目名称
    
    比如我的项目名称是demo1在浏览器中输入为**http://localhost:8080/demo1/a.jsp ${pageContext.request.contextPath**}或**<%=request.getContextPath()%>**取出来的就是**/demo1**,而"/"代表的含义就是**http://localhost:8080**
    
    故有时候项目中这样写**${pageContext.request.contextPath}/a.jsp**