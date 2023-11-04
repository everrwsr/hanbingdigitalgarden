---
{"dg-publish":true,"permalink":"/03evermemo/02code/git/01programming git commit message/","dgPassFrontmatter":true,"noteIcon":"","created":"","updated":""}
---


  git add . // 更新到暂存区
  git commit -m "feat: 添加 Hello.ts 页面" // 更新到资源库
    // 提交规范:
    1. feat: 增加新功能
    2. fix: 修复bug
    3. docs: 只改动了文档相关内容
    4. styles: 不影响代码的含义的改动，如：去掉空格、缩进、增删分号等
    5. build: 构造工具或者外部依赖的改动 如webpack、npm等
    6: refactor: 代码重构时作用
  git commit --amend // vim中修改内容信息
  git push // 提交至远程仓库

  git branch -D <BranchName> // 删除本地分支
    git push origin --delete <BranchName>  // 真正的删除远程分支



https://www.vonmo.cn/archives/8032/


