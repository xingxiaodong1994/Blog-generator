---
title: git 分支建立与同步
date: 2018-12-12 17:45:57
tags:
---
- 如果`git status`告诉你有文件被修改过，用`git diff`可以查看修改内容。
- `git log --pretty=oneline`查看以前的提交
- `git reflog` # 查看命令历史
- `git reset --hard commit_id` # 回退到历史版本
- `git checkout -- [文件名]` # 撤销修改到最近一次git commit或git add时的状态。
- 注意：文件删除错误，也可以通过`git checkout -- [文件名]`回复。
- `git reset HEAD [文件名]` # 丢弃已经添加到暂存区（git add .）的修改。

以前 我只会建立一个本地分支和远程分支。
当我们运行`git init`后会自动建立一个本地主分支`master`
然后我们会去github上建立一个远程仓库，运行GitHub给的命令

` git remote add origin git@github.com:[xxxxxx].git`
这条命令就会把我们本地仓库和远程关联起来。

然后我们运行` git push -u origin master`
就可以把本地主分支内容提交的GitHub远程主分支仓库。

注意：
我们第一次推送master分支时，加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。

以后我们只要运行`git push origin master`就可以推送最新修改

`git push origin [新远程分支名字]` # 建立一个远程新分支

查看分支：`git branch`

创建分支：`git branch <name>`

切换分支：`git checkout <name>`

创建+切换分支：`git checkout -b <name>`

合并某分支到当前分支：`git merge <name>`

删除分支：`git branch -d <name>`

克隆git仓库到本地: `git clone git@github.com:[xxxxxx].git`

当Git无法自动合并分支时，就必须首先解决冲突。解决冲突后，再提交，合并完成。
解决冲突就是把Git合并失败的文件手动编辑为我们希望的内容，再提交。

`git log --graph`:查看分支合并图。

修复bug时，我们会通过创建新的bug分支进行修复，然后合并，最后删除；

当手头工作没有完成时，先把工作现场`git stash`一下，然后去修复bug，修复后，再`git stash `pop，回到工作现场。

如果要丢弃一个没有被合并过的分支，可以通过`git branch -D <name>`强行删除。
查看远程库信息，使用`git remote -v`；

本地新建的分支如果不推送到远程，对其他人就是不可见的；

从本地推送分支，使用`git push origin branch-name`，如果推送失败，先用`git pull`抓取远程的新提交；

在本地创建和远程分支对应的分支，使用`git checkout -b branch-name origin/branch-name`，本地和远程分支的名称最好一致；

建立本地分支和远程分支的关联，使用`git branch --set-upstream branch-name origin/branch-name`；

从远程抓取分支，使用`git pull`，如果有冲突，要先处理冲突
命令`git tag <tagname>`用于新建一个标签，默认为HEAD，也可以指定一个commit id；

命令`git tag -a <tagname> -m "blablabla..."`可以指定标签信息；

命令`git tag`可以查看所有标签。