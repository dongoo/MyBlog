---
layout: post
title: "安装使用octopress"
date: 2015-06-28 02:19:11 +0800
comments: true
categories: octocpress
---

折腾了几次了，貌似学会了怎么使用octopress了，现在整理一下。

##环境搭建

###安装Git、Ruby、DevKit、MarkdownPad

1.Git下载：[https://git-scm.com/download/](https://git-scm.com/download/)

2.Ruby下载和DevKit下载：[http://rubyinstaller.org/downloads/](http://rubyinstaller.org/downloads/)

3.MarkdownPad下载：[http://markdownpad.com/](http://markdownpad.com/)

4.百度网盘下载：（适合64位windows）

链接：[http://pan.baidu.com/s/1i38Ia0l](http://pan.baidu.com/s/1i38Ia0l) 密码：p6nj

下载安装完成后需要在Devkit目录下,使用下面命令，手动将ruby与devkit关联

	ruby dk.rb init
<!--more-->
###安装Octopress

克隆Octopress至本地


	git clone git://github.com/imathis/octopress.git octopress
	cd octopress

安装依赖项

	gem install bundler
	bundle install

>由于国内网络原因，安装依赖项时，可能无法正常完成，需要对配置文件进行修改
>
>1.修改软件源
>
	$ gem sources --remove https://rubygems.org/ //删除原软件
	gem sources -a https://ruby.taobao.org/	//添加淘宝的rubygems镜像
	gem sources -l

>2.修改 octopress/ 中的Gemfile（文本编辑器打开），将其中`https://rubygems.org/`修改为`https://ruby.taobao.org/`

###安装Octopress默认主题

    rake install

###新建博客与单页面

1.新建博客

	rake new_post["helloworld"]
	#Creates source/_posts/2015-06-26-helloworld.markdown
	#URL http://ww.lidong.im/blog/2015/06/26/helloworld/index.html

2.新建单页面

	rakenew_page[helloworld]
	#Creates source/helloworld/index.markdown
	
	rakenew_page[helloworld/page.html]
	#Creates source/hellword/page.html

###生成并本地预览

1.生成静态页面

	rake generate

2.本地预览

	rake preview
	#http://localhost:4000

##部署网站至Github

新建仓库

	username.github.io

与octopress目录绑定


	rake setup_github_pages

	rake deploy

将source目录更新到远程仓库

	git add .
	git commit -m 'your message'
	git push origin source







