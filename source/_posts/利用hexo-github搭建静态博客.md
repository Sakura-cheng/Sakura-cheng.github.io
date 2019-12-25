---
title: 利用hexo+github搭建静态博客
date: 2019-09-28 19:53:57
categories:
 - 备忘
tags: 
 - hexo
 - 博客
---

从零开始搭建博客
<!-- more -->
## 安装git

## 安装node.js
[下载node.js](http://nodejs.cn/download/)

安装完成后会附带npm包管理器

为了防止后续下载速度过慢，使用淘宝镜像
```
npm install -g cnpm --registry=https://registry.npm.taobao.org
```

## 安装hexo
```
cnpm install -g hexo-cli
```

## 生成博客
先创建一个blog文件夹

```
hexo init // 生成博客
hexo s // 启动博客
```

## 写一篇博文
```
hexo n "我的第一篇文章"
```
编写完一篇博文后
```
hexo clean // 清理缓存
hexo g // 生成
```

## 安装部署插件
```
cnpm install --save hexo-deployer-git
```

## 修改配置文件
修改blog目录下的_config.yml文件

将_config.yml文件最底部修改为：  
> deploy:  
> &nbsp;&nbsp;&nbsp;&nbsp;type: git  
> &nbsp;&nbsp;&nbsp;&nbsp;repo: https://github.com/Sakura-cheng/Sakura-cheng.github.io.git  
> &nbsp;&nbsp;&nbsp;&nbsp;branch: master

## 部署到远端
```
hexo d
```

## 修改主题
```
git clone https://github.com/iissnan/hexo-theme-next themes/next
```

修改_config.yml文件中
> theme: next