---
layout: post
title: "开篇"
date: 2014-01-14 13:21:29 +0800
comments: true
categories: blog
tags:
- octopress
- github blog
---
很久以前就想写写博客, 随便记点什么. 又想自己写个博客程序练练手, 不过由于种种原因都放弃了. 虽然一直在用为知笔记, 也确实不错, 不过现在是一个装的时代, 不搞个博客出去都不好意思打招呼.

于是想起了日渐流行的把博客放到良心的 [github](https://github.com) 上的做法, 放放狗查查教程, 简单写下设置过程.
<!--more-->
### [附] Windows下安装方法
#### 1. 安装ruby
到 <http://rubyinstaller.org/downloads/> 下载ruby, 如果你不方便安装, 可以下载7zip格式的(我就是用的这种, 办公电脑不方便安装).

> 1. 解压到某文件夹, 如 **D:\ruby**
> 2. 添加到环境变量, 如 **D:\ruby\bin**

#### 2. 安装devkit
下载devkit, 右键解压到一个文件夹(如d:\devkit)
```bash
ruby dk.rb init
ruby dk.rb install
```
**注意:**
运行install前得编辑config.yml, 在最后面添加 **`- d:/ruby`** 一行, 注意最前面的 **`-`** 一定得加上.

#### 3. 添加环境变量, 方便使用中文
LANG=zh_CN.UTF-8 和 LC_ALL=zh_CN.UTF-8

#### 4. 安装Octopress
4.1 安装Octopress
```bash
git clone git://github.com/imathis/octopress.git myblog
cd myblog    //这边会有提示信息, yes就行
ruby --version  //Ruby的版本需要在1.9.3+版本
```
4.2 更换 gem 源(国内环境, 你懂的)
```bash
gem sources -r http://rubygems.org/
gem sources -a http://ruby.taobao.org/
gem sources -l
```

4.3 安装插件
```bash
gem install bundler
bundle install
```

4.4 安装Octopress 主题
```bash
rake install
```

4.5 修改配置
修改配置文件_config.yml, 修改url、title、subtitle、author等等, 可以把评论disqus加上, google+等等, 择需加上.

4.6 创建github仓库 (如果你想要这样的网址 **username.github.io**, 仓库名得写成这样的: **username.github.io**, 好像 **username.github.com** 的不行了, github pages都转到github.io了)

4.7 本地配置github分支
```bash
rake setup_github_pages
```
当命令提示你输入github URL时, 输入刚才建立的git地址

4.8 好了, 写文章吧
```bash
rake new_post["my first blog"]
```
在 `myblog/source/_post` 下生成一个 `**.makedown` 的文件, 编辑文章即可.

4.9 生成, 预览
```bash
rake generate
rake preview
```
在浏览器中打开 http://127.0.0.1:4000 就可在本地调试页面

4.10 git提交
```bash
rake deploy
```

4.11 别忘了把源代码同步到 `github` 上.
```bash
git add .
git commit -m 'your message'
git push origin source
```

4.12 打完收工.

#### 参考文章 <http://www.xiaoche.me/blog/2012/01/18/install-octopress/>
<!--more-->
