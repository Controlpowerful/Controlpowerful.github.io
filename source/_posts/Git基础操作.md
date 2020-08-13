---
title: Git基本认知
date: 2020-08-13 13:33:20
tags: Git
categories: Git
thumbnail: /img/thumb/thumb-1.jpg
---
杨帆,启航!
<!-- more -->

# Git基操
2020年,你可以不会任何一门编程语言但是请一定熟练的掌握Git的操作;因为它真的是太强大方便了~

Linux下默认是预装好了Git的,So let's do this.

## 创建工作区
Git的工作区呢,说白了就是我们的一个目录,所以创建一个工作区就直接mkdir new folder.

``` shell
mkdir learngit
```

## 暂存区
在说明暂存区之前,先来生成一个`git仓库`

``` shell
git init 
```

`git init` 会初始化创建一个仓库 ---> `.git`

好的,让我们来介绍下暂存区吧,顾名思义它是一个暂时存储的地方是`临时的`,在`.git`下的`index`文件就是暂存区域也被称之为 ---> `stage`

## 版本库
`.git`文件就是一个版本库,但它被称为`本地版本库`

版本库分为两个部分
- stage (index)
- master

其中stage是暂存区,`master`是一个`分支`,它是在我们创建版本库时自动生成的


让我们来整理下毕竟初学者 like me一样会双眼发直
1. 工作区就是一个目录
2. git init 在工作区里面创建一个名为`.git`的`本地版本库`
3. 暂存区其实是`.git`下叫做`index`的文件,被称为stage(index)
4. master是在版本库创建自动生成的,它是一个`分支`
