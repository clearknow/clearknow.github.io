---
layout: post
title:  "python 爬虫"
date:   2020-05-29 13:00:05
categories: python
tags: python 爬虫 词云 贴吧 Java
---


* content
{:toc}

>最近经常逛贴吧，突然想想，贴吧吧友每天再发啥呢！于是就有了下面这些







## 找了一个Java吧，看他们源码

*源码主要的部分
	
	*网址结构：
		https://tieba.baidu.com/f?kw=jAVA&ie=utf-8&pn=0
		将kw=xxx该成目标贴吧就可以随便爬了
		页数的话是50为一页，第一页pn=0
		
	*页码
	
		主要是用a标签，渲染所用的类为：pagination-item
		
	*内容
	
		发帖内容标签div，所用类：threadlist_abs', 'threadlist_abs_onlyline

## 过程

*所用的库

	*Requests		
	*BeautifulSoup
	*numpy
	*Image
	*jieba
	*WordCloud
	
## 坑
	*对requests获取的内容进行转换
		
		最好使用html5lib 主要是它会自行补缺的标签，
		其他的要么吧缺省的标签删除或者不处理质量的 lxml  parse.html等
		因为我感觉使用beautifulSoup他只会在html里面的进行搜索，外面就搜索不到
		而实际上soup里面是有
	*使用beautifulSoup进行标签查找
		
		1.使用下面这种格式会好点，不然有时页数差不到的，说是不支持类中含有xx-xx
		soup.find_all('a', attrs={'class': 'pagination-item'}
		2.进行一个标签有多个类时，使用字典，同样有1的情况也是按上述方法
		soup.find_all("div", class_={'threadlist_abs', 'threadlist_abs_onlyline'})
	
##镇楼
		
	*查了下，还是广告多，贴吧感觉好多都沦陷了
	
![image03](/image/image2.jpg)
















