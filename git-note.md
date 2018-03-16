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
# 222
```


## 参考

* [git-doc-zh](https://git-scm.com/book/zh/v1/Git-%E5%88%86%E6%94%AF-%E5%88%86%E6%94%AF%E7%9A%84%E6%96%B0%E5%BB%BA%E4%B8%8E%E5%90%88%E5%B9%B6)
* [廖雪峰的官方网站](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/001375840038939c291467cc7c747b1810aab2fb8863508000)





