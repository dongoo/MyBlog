---
layout: post
title: "octopress配置"
date: 2015-07-01 13:35:28 +0800
comments: true
categories: octopress
---

##基本设置

octopress主配置文件在 octopress/_config.yml中


	url: http://dongoo.github.io	#网站网址
	
	title: 分享技术，分享快乐 	#网站标题
	
	subtitle: A blogging framework for hackers.	#网站副标题
	
	author: dongoo	#网站作者
	
	simple_search: https://www.google.com/search	#搜索引擎链接
	
	description:	#网站描述，会出现在首页页面的 meta 中的 description中

<!--more-->

##设置导航栏

打开文件source\_includes\custom\navigation.html，默认情况下如下所示：

	<ul class="main-navigation"> 
	<li><a href="{{ root_url }}/">Blog</a></li> 
	<li><a href="{{ root_url }}/blog/archives">Archives</a></li> 
	</ul>

可以将Blog和Archives修改为首页和归档，不过记得将包含有中文的文件保存为无BOM的UTF-8编码格式。也可以在此添加一个标签页，比如加上一个关于，我们可以按下面步骤实现：

使用命令rake new_page['about']创建一个页面，页面路径为source\about\index.markdown;

修改上面的navigation.html为：

	<ul class="main-navigation"> 
	  <li><a href="{{ root_url }}/">首页</a></li> 
	  <li><a href="{{ root_url }}/blog/archives">归档</a></li> 
	  <li><a href="{{ root_url }}/about">关于</a></li> 
	</ul>

##首页文章摘要输出

打开octopress/_config.yml文件

	excerpt_link: "Continue reading &rarr;"  # 现在在摘要输出文章下面继续阅读链接的内容，可以将“Continue reading”修改为中文“继续阅读”，显示时就是中文。
	
	excerpt_separator: "<!--more-->"	摘要输出的

##添加版权信息
这里所说的版权声明是指每篇文章后面的版权信息

首先source\_includes\post目录中新建license.html文件，文件内容如下：（注意将其中的相关信息，修改成你自己的信息）

	<div class="sharing">
	{% if site.post_license %}
	<div style="font-size:14px;border-bottom: #bbbbbb 1px solid; border-left: #bbbbbb 1px solid; background: #f6f6f6; height: 100px; border-top: #bbbbbb 1px solid; border-right: #bbbbbb 1px solid" > 
	<div style="margin-top: 5px; float: left; margin-left: 10px; margin-right: 10px"> 
	<div style="line-height: 200%; margin-top: 10px; color: #000000"> 
	作者： <a href="http://www.lidong.im/">dongoo</a> <br> 
	出处： <a href="http://www.lidong.im/">http://www.lidong.im/</a> 
	本作品采用<a rel="license" href="http://creativecommons.org/licenses/by/3.0/cn/">知识共享署名 3.0 中国大陆许可协议</a>进行许可。<br />
	<a rel="license" href="http://creativecommons.org/licenses/by/3.0/cn/"><img alt="知识共享许可协议" style="border-width:0" src="https://i.creativecommons.org/l/by/3.0/cn/80x15.png" /></a>
	</div>
	</div></div>{% endif %}

##添加评论
Octopress本身是不支持评论功能，我们需要借用第三方的评论，国内有多说，国外有disqus。

我使用的是disqus。首先需要在Disqus注册一个账号，登录后点击Dashboard，然后添加站点信息

在_config.yml文件中进行下面设置

	# Disqus Comments 
	disqus_short_name: name   # disqus—name为添加站点信息时的Site Shortname 
	disqus_show_comment_count: true

到此为止需要配置的基本都OK了
当然参考其它的文章

参考来源：

[http://www.cnblogs.com/oec2003/archive/2013/05/31/3109577.html](http://www.cnblogs.com/oec2003/archive/2013/05/31/3109577.html)

[http://octopress.org/docs/configuring/](http://octopress.org/docs/configuring/)