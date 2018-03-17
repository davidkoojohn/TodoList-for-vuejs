## git 分支开发笔记

## 创建与合并分支

> 每次提交，Git都把它们串成一条时间线，这条时间线就是一个分支。在Git里，这个分支叫主分支，即`master`分支。`HEAD`严格来说不是指向提交，而是指向 `master`，`master`才是指向提交的，所以，`HEAD`指向的就是当前分支。

**`总结`: HEAD 就是当前工作区能看到的。**

```
# 首先，我们创建dev分支，然后切换到dev分支：
git branch -b dev
# Switched to a new branch 'dev'

# 上面命令 = 
git branch dev
git checkout dev

# 查看本地分支
git branch

# ... 工作 ing

# 合并分支
git merge dev
# 删除分支
git branch -d dev

# 禁用 Fast forward
git merge --no-ff -m "merge with no-ff" dev

git stash
git stash list
git stash pop
# git stash pop === git stash apply + git stash drop

git branch -d feature-vulcan
# error: The branch 'feature-vulcan' is not fully merged.
# If you are sure you want to delete it, run 'git branch -D feature-vulcan'.

# 强行删除
git branch -D feature-vulcan

git remote -v
# origin  git@github.com:michaelliao/learngit.git (fetch)
# origin  git@github.com:michaelliao/learngit.git (push)
# 上面显示了可以抓取和推送的origin的地址。如果没有推送权限，就看不到push的地址。

git push origin master
git push origin dev
# 但是，并不是一定要把本地分支往远程推送，那么，哪些分支需要推送，哪些不需要呢？
# master分支是主分支，因此要时刻与远程同步；
# dev分支是开发分支，团队所有成员都需要在上面工作，所以也需要与远程同步；
# bug分支只用于在本地修复bug，就没必要推到远程了，除非老板要看看你每周到底修复了几个bug；
# feature分支是否推到远程，取决于你是否和你的小伙伴合作在上面开发。

git clone git@github.com:***
# 只能看到本地的master分支 git branch

# 如果要在dev分支上开发，就必须创建远程origin的dev分支到本地，于是他用这个命令创建本地dev分支：
git checkout -b dev origin/dev
# 现在，他就可以在dev上继续修改，然后，时不时地把dev分支push到远程：
git push origin dev
# no tracking information

git pull <remote> <branch>
# If you wish to set tracking information for this branch you can do so with:

git branch --set-upstream dev origin/<branch>
# or
git branch --set-upstream-to=origin/<branch> dev
# Branch dev set up to track remote branch dev from origin.

git reset HEAD^
git reset HEAD~100
git reset 3628164

# 未添加的 Untracked
# 暂存区 Stage
# 工作区 work dict

# 是工作区(work dict)和暂存区(stage)的比较
git diff
# 是暂存区(stage)和分支(master)的比较
git diff --cached

git checkout -- file
# 命令中的--很重要
git reset HEAD file

git rm
```


## 参考

* [git-doc-zh](https://git-scm.com/book/zh/v1/Git-%E5%88%86%E6%94%AF-%E5%88%86%E6%94%AF%E7%9A%84%E6%96%B0%E5%BB%BA%E4%B8%8E%E5%90%88%E5%B9%B6)
* [廖雪峰的官方网站](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/001375840038939c291467cc7c747b1810aab2fb8863508000)





