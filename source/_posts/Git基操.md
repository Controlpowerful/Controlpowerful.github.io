---
title: Git基操
date: 2020-08-13 15:04:33
tags: Git
categories: Git
thumbnail: /img/thumb/thumb-2.jpg
---
熟悉Git的基本操作!
<!-- more -->

# 暂存区
上篇文章讲到`暂存区`是`版本库`下的index文件,它是用来存储临时提交文件的,那怎么提交呢???

``` Git
git add readme
```

上面的命令会把`readme`文件提交到暂存区存放,这时候你会发现终端的shell出现了变化(其实是一个提示)

![](/img/git/1.png)

该命令把工作区`readme`提交到了`暂存区`

## 检查状态
`git status`检查提交文件的状态

``` Git
git status
```

Look,git给了我们个提示

![](/img/git/2.png)

询问我们是否要提交,同时也给了我们方案告诉我们把文件丢出去的指令

`git status`指令只要你在工作区对文件进行任意修改,就可以查看当前状态

### 本地版本库
上面图片中看到git询问我们是否要提交,提交只需要一条非常简单的命令就可以

``` Git
git commit -m "message"
```

`commit`命令会把存放在暂存区的文件上传到`本地版本库`,注意是**本地版本库**

![](/img/git/3.png)

提交完成后,发现上面的X已经消失了,再次`git status`也没有回显,证明我们的提交成功了!

wait,wait,你之前不是说什么`master`什么的,到底是个什么东西啊??

### 历史查看
git之所以这么强大点就在于它是`分布管理`

我们刚才所提交的只不过是在我们本地操作,他的流程是这样的
1. 工作区 -----> git add . ------> 暂存区
2. 暂存区 -----> git commit -m "message" ------> 本地版本库


![](/img/git/4.png)

当我们在创建版本库时,git自动帮我们创建了一个分支`master`,`git commit`就是往`master`分支做出提交

So,让我们看看到底什么是分支和`master`

既然是分支那就有很多东西在下面,`git log`查看**所有**`commit`过的提交历史,并且是**从新到旧**的形式排列的.


``` Git
git log
```

![](/img/git/5.png)


### HEAD指针
两张图片都出现了HEAD,世界上绝对不会有一样东西偶然出现2次

HEAD是一个指针,负责指向`分支`的指针,你在哪HEAD就指向哪;后面写分支的时候在仔细描述HEAD,他就是指哪打哪没啥好说的~

### 版本回调
在上面我们对`readme`文件进行了提交,我们现在要对其进行修改再次提交

change:
``` shell
This is a example
My name is Zhouenlai
```

再次提交:
``` shell
git add .
git commit -m "change"
```
`git log`查看下提交记录

![](/img/git/6.png)

问题出现了,刚才发呆把不该发送的信息提交了出去! 不慌,`版本回调`是git的一个特点,它允许你犯错!

``` shell
git reset --hard HEAD^ # 回到当前版本的上一个版本

or:

git reset --hard HEAD~1
```
好的,奇迹出现了错误不见了,HEAD重新指向了第一次提交 -----> `first`
![](/img/git/7.png)

![](/img/git/8.png)

hold on! 我现在就要回到刚才那个版本,现在没了,你把他删除了! no,我并没有把`change`删除它只不过暂时消失了

``` shell
git reflog # 查看操作记录
```

![](/img/git/9.png)

我反正是看到了`change`的哈希,reset回去即可

``` shell
git reset --hard hash
```

git log发现已经回到刚才的版本! (文件也同样回调)

![](/img/git/10.png)

### git diff
最后一个小技巧 -----> `git diff file` 查看文件修改差异  

**注意**:`git diff`只能在**工作区**下查看

eg: 
``` shell
My name is Liuli!
```

![](/img/git/11.png)
