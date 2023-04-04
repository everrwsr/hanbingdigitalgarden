---
{"url":"https://blog.csdn.net/liaowhgg/article/details/84961837?spm=1001.2014.3001.5502","title":"(8 条消息) Git 常用操作指令_NeroAsmar 的博客 - CSDN 博客_git 常用操作命令","date":"2023-02-26 13:20:47","tag":null,"summary":null,"dg-publish":true,"permalink":"/webpage/(8 条消息) Git 常用操作指令_NeroAsmar 的博客 - CSDN 博客_git 常用操作命令/","dgPassFrontmatter":true}
---

## 1 常用

<table><thead><tr><th align="left">命令</th><th align="left">说明</th></tr></thead><tbody><tr><td align="left"><code>git init</code></td><td align="left">把指向的目录变成 Git 可以管理的仓库</td></tr><tr><td align="left"><code>git add readme.txt</code></td><td align="left">把 readme.txt 加入仓库</td></tr><tr><td align="left"><code>git commit -m “wrote a readme file”</code></td><td align="left">把文件提交到仓库并进行说明</td></tr><tr><td align="left"><code>git status</code></td><td align="left">查看仓库状态是否被修改</td></tr><tr><td align="left"><code>git diff readme.txt</code></td><td align="left">查看 readme.txt 修改详情</td></tr><tr><td align="left"><code>git log</code></td><td align="left">查看提交日志</td></tr><tr><td align="left"><code>git log --pretty=oneline</code></td><td align="left">简洁查看提交日志</td></tr><tr><td align="left"><code>git reset --hard HEAD^</code></td><td align="left">退回到上一个版本，HEAD^^ 上两个版本，HEAD-100 上 100 个版本</td></tr><tr><td align="left"><code>git reset --hard 1094a</code></td><td align="left">回到版本号前面为 1094a 的文件版本</td></tr><tr><td align="left"><code>git reflog</code></td><td align="left">记录每一次命令（可以查看版本号）</td></tr><tr><td align="left"><code>git diff HEAD -- readme.txt</code></td><td align="left">提交文件后，查看工作区和版本库中有什么不同</td></tr><tr><td align="left"><code>git checkout -- readme.txt</code></td><td align="left">把 readme.txt 文件从版本库替换工作区版本，可以用作把工作区的修改全部撤销，恢复工作区误删文件，但是只能恢复到最新一次修改后的文件，会丢失修改提交内容</td></tr><tr><td align="left"><code>git reset HEAD readme.txt</code></td><td align="left">把 readme.txt 文件暂存区的修改撤销，重新放回工作区, HEAD 表示最新版本</td></tr><tr><td align="left"><code>git rm test.txt</code></td><td align="left">从版本库删 test.txt, 之后可<code>git commit -m "remove test.txt"</code>提交删除报告</td></tr></tbody></table>

## 2 Github

<table><thead><tr><th align="left">命令</th><th align="left">说明</th></tr></thead><tbody><tr><td align="left"><code>ssh-keygen -t rsa -C "youremail@example.com"</code></td><td align="left">创建 SSH Key, 实例改为自己的邮箱</td></tr><tr><td align="left"><code>git remote add origin git@github.com:yourself/learngit.git</code></td><td align="left">把本地 learngit 仓库关联 yourself 的 learngit 仓库</td></tr><tr><td align="left"><code>git push -u origin master</code></td><td align="left">把本地库的 master 分支内容推送到远程仓库。由于远程库是空的，我们第一次推送 master 分支时，加上了 - u 参数，Git 不但会把本地的 master 分支内容推送的远程新的 master 分支，还会把本地的 master 分支和远程的 master 分支关联起来，在以后的推送或者拉取时就可以简化命令<code>git push origin master</code>。</td></tr><tr><td align="left"><code>git clone git@github.com:michaelliao/gitskills.git</code></td><td align="left">从远程库克隆</td></tr></tbody></table>

## 3 分支管理

### 3.1 基本

<table><thead><tr><th align="left">命令</th><th align="left">说明</th></tr></thead><tbody><tr><td align="left"><code>git branch dev</code></td><td align="left">创建 dev 分支</td></tr><tr><td align="left"><code>git checkout dev</code></td><td align="left">切换到 dev 分支</td></tr><tr><td align="left"><code>git checkout -b dev</code></td><td align="left">创建 dev 分支，并切换到 dev 分支，-b 表示创建并切换相当于<code>git branch dev</code>创建分支 +<code>git checkout dev</code>切换分支</td></tr><tr><td align="left"><code>git branch</code></td><td align="left">列出所有分支，当前分支前面有 * 号</td></tr><tr><td align="left"><code>git merge dev</code></td><td align="left">把指定 dev 分支合并到当前所在分支, Fast forward(快速合并)</td></tr><tr><td align="left"><code>git branch -d dev</code></td><td align="left">删除 dev 分支</td></tr><tr><td align="left"><code>git branch -D dev</code></td><td align="left">强行删除 dev 分支，在分支未合并的时候可以强行删除</td></tr><tr><td align="left"><code>vi readme.txt</code></td><td align="left">编辑 readme.txt，删除分支冲突</td></tr><tr><td align="left"><code>git log --graph --pretty=oneline --abbrev-commit</code></td><td align="left">查看分支合并情况</td></tr><tr><td align="left"><code>git merge --no-ff -m "merge with no-ff" dev</code></td><td align="left">–no-ff 参数，表示禁用 Fast forward,-m 添加合并描述，把 dev 分支合并到当前分支</td></tr></tbody></table>

**分支策略在实际开发中，我们应该按照几个基本原则进行分支管理：**

1.  master 分支应该是非常稳定的，也就是仅用来发布新版本，平时不能在上面干活
2.  干活都在 dev 分支上，也就是说，dev 分支是不稳定的，到某个时候，比如 1.0 版本发布时，再把 dev 分支合并到 master 上，在 master 分支发布 1.0 版本
3.  多人协作时候每个人都在 dev 分支上干活，每个人都有自己的分支，时不时地往 dev 分支上合并就可以了。

### 3.2 工作区操作

<table><thead><tr><th align="left">命令</th><th align="left">说明</th></tr></thead><tbody><tr><td align="left"><code>git stash</code></td><td align="left">储存当前工作区到 stash</td></tr><tr><td align="left"><code>git stash list</code></td><td align="left">查看被储存的 stash 内容</td></tr><tr><td align="left"><code>git stash pop</code></td><td align="left">把 stash 内容恢复到工作区并删除 stash 区</td></tr><tr><td align="left"><code>git stash apply</code></td><td align="left">stash 内容恢复到工作区，但不删除 stash 区</td></tr><tr><td align="left"><code>git stash drop</code></td><td align="left">删除 stash 区</td></tr></tbody></table>

### 3.3 多人协作

<table><thead><tr><th align="left">命令</th><th align="left">说明</th></tr></thead><tbody><tr><td align="left"><code>git remote</code></td><td align="left">查看远程库信息</td></tr><tr><td align="left"><code>git remote -v</code></td><td align="left">显示更详细的远程库信息</td></tr><tr><td align="left"><code>git push origin dev</code></td><td align="left">推送 dev 分支到远程库</td></tr><tr><td align="left"><code>git checkout -b dev origin/dev</code></td><td align="left">创建远程 origin 的 dev 分支到本地并切换至 dev 分支</td></tr><tr><td align="left"><code>git pull</code></td><td align="left">把最新提交抓取下来</td></tr><tr><td align="left"><code>git branch --set-upstream branch-name origin/branch-name</code></td><td align="left">创建本地分支与远程分支的联系</td></tr></tbody></table>

### 3.4 Rebase 整理

<table><thead><tr><th align="left">命令</th><th align="left">说明</th></tr></thead><tbody><tr><td align="left"><code>git rebase</code></td><td align="left">将分叉提交变成一条直线</td></tr></tbody></table>

## 4 标签管理

先切换到需要打标签的分支上

<table><thead><tr><th align="left">命令</th><th align="left">说明</th></tr></thead><tbody><tr><td align="left"><code>git tag v1.0</code></td><td align="left">给最新的 commit 打上 v1.0 的标签</td></tr><tr><td align="left"><code>git tag</code></td><td align="left">查看所有的标签</td></tr><tr><td align="left"><code>git tag v0.9 f52c633</code></td><td align="left">给指定的 f52c633 commit 打上标签</td></tr><tr><td align="left"><code>git show v0.9</code></td><td align="left">查看 v0.9 标签的详情</td></tr><tr><td align="left"><code>git tag -a v0.1 -m "version 0.1 released" 1094adb</code></td><td align="left">给指定 v0.1 标签添加说明文字，1094adb 为版本号</td></tr><tr><td align="left"><code>git tag -d v0.1</code></td><td align="left">删除 v0.1 标签，因为创建的标签都只存储在本地，不会自动推送到远程。所以，打错的标签可以在本地安全删除</td></tr><tr><td align="left"><code>git push origin v1.0</code></td><td align="left">推送指定 v1.0 标签到远程</td></tr><tr><td align="left"><code>git push origin --tags</code></td><td align="left">推送全部标签到远程</td></tr><tr><td align="left"><code>git push origin :refs/tags/v0.9</code></td><td align="left">删除远程到标签 v0.9</td></tr></tbody></table>

注意⚠️：标签总是和某个 commit 挂钩。如果这个 commit 既出现在 master 分支，又出现在 dev 分支，那么在这两个分支上都可以看到这个标签。

**⚠️系个人整理, 如有不正确或者待完善的地方请留言提出…**