---
layout: post
title: "octopress的进阶使用"
date: 2015-07-02 09:42:50 +0800
comments: true
categories: octopress
---
使用octopress是有时候需要一些小功能，使用下面的代码一些插件代码，可以快速实现

##插入图片

{% codeblock %}

{% img [class names] /path/to/image [width] [height] [title text [alt text]] %}
{% endcodeblock %}

##插入视频

	{ % video url/to/video [width height] [url/to/poster] %}


<!--more-->
##插入代码片段

	{ % codeblock [lang:language] [title] [url] [link text] %} 
		# ｛和%之间不能有空格
	code snippet
	{ % endcodeblock %} 
		#｛和%之间不能有空格


##插入代码文件


    {% include_code [title] [lang:language] path/to/file %}	
		#path值指的是_config.yml中code_dir的值
    


个人认为这几个插件比较常用一点，就只介绍这几个，其它有需要请参考官方文档吧:)

参考：[http://octopress.org/docs/plugins/](http://octopress.org/docs/plugins/)



