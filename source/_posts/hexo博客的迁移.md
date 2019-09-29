---
title: hexo博客的迁移
date: 2019-09-29 22:35:10
categories:
 - 备忘
tags:
 - hexo
 - 博客
---

前两天刚[利用hexo+github搭建静态博客]("https://www.baidu.com")，今天想到以后如果换电脑，肯定是需要将hexo博客进行迁移的，于是便查阅了相关教程，在此做一个记录
<!-- more -->
## 思路
整个方法的思路是在博客原有的库中新建一个hexo分支来存放hexo生成的文件，而原有的master分支只用来存储hexo部署后的静态文件

## 步骤
先从远端将yourname.github.io库clone下来
```
git clone git@github.com:yourname/yourname.github.io.git
```
打开git bash新建一个hexo分支
```
git branch hexo  // 创建hexo分支
git checkout hexo  // 跳转到hexo分支
```
在hexo分支下进行hexo的安装和博客的搭建([见此]("https://www.baidu.com"))

在新建博文后先将hexo文件push到远端(此时是在hexo分支下进行)
```
git add .
git commit -m ""
git push origin hexo
```
再进行静态文件的推送
```
hexo d
```
由于之前在站点配置文件_config.yml中设置的分支为master，而hexo文件是在hexo分支上的，两者不会相互影响
> deploy:  
> &nbsp;&nbsp;&nbsp;&nbsp;type: git  
> &nbsp;&nbsp;&nbsp;&nbsp;repo: https://github.com/Sakura-cheng/Sakura-cheng.github.io.git  
> &nbsp;&nbsp;&nbsp;&nbsp;branch: master

## 迁移
当换新电脑时，只需将hexo分支上存放的hexo文件clone下来，再进行相应的hexo和相关插件的安装就行了(注意：这时就不需要执行hexo init命令进行初始化了)