title: 使用Hexo搭建GitHub Pages
date: 2015-12-24 10:25:07
tags: [Git Page, Hexo]
categories: 安装配置篇
original: false
---
作为一名程序媛，一直想要一个属于自己的博客。最近心情好，在同事的帮助下，捣鼓了一下GitHub Pages。本文简单介绍如何使用Hexo来搭建自己的GitHub博客。

<!-- more -->
## 创建Github Repo
### 登录GitHub账号，点击New repository
![GitHub首页][1]
### 填写Repo信息，创建Repo
> Repo的名称必须为{github账号名称}.github.com，填好名称后(我已经创建过该名称的repo，故出现红色提示，不用管)，点击下面的绿色按钮'Create repository'

![创建GitHub Repo][2]
### 使用GitHub页面生成器
> 选择 'Settings' Tab，点击'Launch automatic page generator'按钮

![Launch automatic page generator][3]
### 选择主题并发布
> 选择喜欢的主题，Publish page

![选择主题并发布][4]
### 访问你的GitHub Page吧
> https://{GitHub账号名称}.github.io
> 
> 也许你觉得GitHub自带的主题不够酷炫，那么你可以使用[Hexo](http://hexo.io/)来丰富你的博客，现在开始吧！

## 使用Hexo搭建你的GitHub Pages
### 安装nodeJS
+ 参考[nodeJS官网](https://nodejs.org)

### 安装node npm包管理器
```shell
sudo apt-get install npm
```

### 全局安装Hexo
```shell
sudo npm install -g hexo
```

### 创建博客目录
```shell
mkdir Blog
```

### 初始化Hexo文件夹
```shell
cd Blog
hexo init
```

### 安装Hexo依赖的nodeJS模块(package.json已定义相关依赖)
```shell
# 使用淘宝镜像会更快一点
npm install --registry=https://registry.npm.taobao.org
```

### 生成Hexo所需Pages
```shell
hexo g
```

### 启动本地Server
```shell
hexo s
```

### 访问本地博客
http://localhost:4000

### 安装部署到GitHub的nodeJS模块
```shell
npm install hexo-deployer-git --registry=https://registry.npm.taobao.org --save
```

### 提交到GitHub创建的仓库
```shell
# _config.yml文件，最后加上部署配置
deploy:
  type: git
  message: "create blog"
  branch: master
  repo: https://github.com/{name}/{name}.github.com.git
```
```shell
hexo d
```
+ 之后需要你输入GitHub的用户名和密码，结束后便将本地的Hexo生成的一系列文件提交到远程仓库了，现在你可以再次访问你的GitHub Page的主页啦！
+ Hexo默认使用的是landscape的主题，是不是觉得不能突显你的逼格，不用担心，Hexo给你提供了非常丰富的主题，[请戳这](https://hexo.io/themes/)，现在你可以根据自己的需求搞起你的博客啦！
+ 换了套主题，别忘了重新生成你的页面哦！`hexo g`一下


  [1]: http://7xpg8c.com1.z0.glb.clouddn.com/Screenshot%20-%202015%E5%B9%B412%E6%9C%8824%E6%97%A5%20-%2010%E6%97%B657%E5%88%8601%E7%A7%92.png
  [2]: http://7xpg8c.com1.z0.glb.clouddn.com/Screenshot%20-%202015%E5%B9%B412%E6%9C%8824%E6%97%A5%20-%2010%E6%97%B657%E5%88%8656%E7%A7%92.png
  [3]: http://7xpg8c.com1.z0.glb.clouddn.com/Screenshot%20-%202015%E5%B9%B412%E6%9C%8824%E6%97%A5%20-%2010%E6%97%B659%E5%88%8609%E7%A7%92.png
  [4]: http://7xpg8c.com1.z0.glb.clouddn.com/Screenshot%20-%202015%E5%B9%B412%E6%9C%8824%E6%97%A5%20-%2011%E6%97%B600%E5%88%8608%E7%A7%92.png
