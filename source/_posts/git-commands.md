title: Git常用命令
date: 2015-12-28 12:39:55
tags: [Git]
categories: 常用命令篇
original: false
---
本文记录工作中常用的Git命令，不定期更新中...

<!-- more -->

#### 设置Git用户名和Email
>git config --global user.name "John Smith"
>git config --global user.email john@example.com

#### 让Git记住你是如何解决某个文件的两个版本之间的conflict，这样在下次Git遇到同样的文件在相同的两个版本间发生冲突时，可以自动帮你使用相同的方法解决冲突
> git config --global rerere.enabled true

#### 将Git默认的编辑器配置成vim
> git config –global core.editor vim

#### 初始化git仓库
> git init

#### 添加远程仓库
> git remote add origin git@github.com:michaelliao/learngit.git

#### 克隆develop分支上的源码
> git clone (-b develop)git@github.com:michaelliao/gitskills.git

#### 将改动提交到暂存区
> git add welcome.txt

#### 将改动提交到本地仓库并添加注释
> git commit -m "initialized"

#### 列出文件状态, staged, unstaged, and untracked.
> git status

#### 查看git 提交日志（最近３条）
> git log -3

#### 查看git log 包含文件改动信息，添加或删除了多少行
> git log --stat

#### 检出命令
> git checkout 
--文件　－－ 撤销工作区尚未提交的文件的修改或者删除
-b 分支　－－　创建并切换到该分支
分支　－－ 切换分支
commit ID　－－　将文件恢复到某次提交

#### 查看修改后的文件与版本库文件的差别
> git diff

#### 删除一些没有 git add的文件
> 查看哪些文件和目录会被删除
> git clean -nd

> 真正删除多余的目录和文件
> git clean -fd

#### 保存当前的工作进度，会分别对暂存区和工作区的状态进行保存
> git stash 

#### 显示进度列表，可以多次保存工作进度，并且在恢复的时候进行选择
> git stash list

#### 清除本地stash
> git stash clear

#### 应用某个stash
> git stash apply stash@{0}

#### 如果不使用任何参数，会恢复最近保存的工作进度
如果提供<stash>参数（来自于git stash list显示的进度列表），则从该stash中恢复
> git stash pop [--index] [<stash>]

#### 版本回退。HEAD表示当前的版本，即最新提交，上一个版本就是HEAD^，上上一个版本就是HEAD^^，当然往上100个版本写100个^比较容易数不过来，所以写成HEAD~100。
> git reset HEAD

#### 版本回到某次提交
> git reset --hard [commit id]

#### 撤销暂存区中readme.txt 的修改
> git reset HEAD readme.txt

#### 记录了使用Git时所使用过的命令，这样就可以回退到某个版本了
> git reflog

#### develop分支上的改动需提交到本地。切换到master分支，将develop分支上的改动merge到master分支上
> git merge develop

#### 合并命令
> git merge --no-ff -m "merged bug fix 101" develop
将develop分支上的改动merge到master分支上。
合并分支时，加上--no-ff参数就可以用普通模式合并，合并后的历史有分支，能看出来曾经做过合并，而fast forward合并就看不出来曾经做过合并。

#### 删除 dev 分支
> git branch -d dev

#### 如果要丢弃一个没有被合并过的分支，可以通过git branch -D <name>强行删除
> git branch -D <name>

#### 查看时间
> ls --full-time .git/index

#### 在本地创建分支并提交到远程
> git checkout -b new_branch_name
> git push -u origin new_branch_name 



