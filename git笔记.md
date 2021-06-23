git init   确定工作区

git add file_name    提交到暂存区

git commit -m "提交说明"  提交暂存区的文件

git status  查看状态

git diff  查看修改内容

git log   提交日志  包括版本id

git reset --hard id   退回到对应的版本

git reflog  查看使用的命令

**git checkout** -- file_name   删除上一次修改/实质上是用上一个版本替换可以还原删除

**git reset** HEAD file_name   删除暂存区的内容

**git rm** file_name   删除工作区的文件需要提交git commit



**远程连接github**

**git remote** add origin git@github.com:autwind18/learngit.git

**git push** -u origin master   origin远程库名字  推送本地仓库最新分支 以后可直接用**git push** **origin master**

**git clone** git@github.com:autwind18/learngit.git   克隆远程库



**分支**

git branch  查看分支

git branch <name>  创建分支

git checkout  <name>  或者 git switch <name>  切换分支

创建+切换   git checkout -b <name> 或 git switch -c <name>

git merge <name>  合并分支

git branch -d <name> 删除分支



**分支管理策略**

通常，在合并分支时，如果可能，git会用Fast forward模式，但这种模式下，删除分支后，会丢掉分支信息。

**git merge --no-ff -m"massage" dev**    加入参数强制禁止fast forward  合并后可以用git log查看



**多人协助**

**git checkout -b dev origin/dev**    抓取远程分支并在本地创建分支

完成作业之后即可推送 git push origin dev，可能会推送失败

可以使用git pull把最新的提交拉取下来，  pull失败可以用git branch --set-upstream-to=origindev dev

来指定本地dev分支与远程分支的连接。pull成功，解决分支冲突再push。

可以用git status然后直接查看两个的不同，使用git lod --graph查看分支合并图（git rebase 把本地为push的分叉提交历史整理成直线）

