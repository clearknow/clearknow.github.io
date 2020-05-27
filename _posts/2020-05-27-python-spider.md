---
layout: post
title:  "python 爬虫"
date:   2020-05-27 21:06:05
categories: python
tags: python 爬虫 电影
---


* content
{:toc}

>闲着无聊，玩玩python，爬取豆瓣电影top250







## 过程

*所用的库

	*Requests
		
		用于获取网址资源，目前网站基本会识别脚本来说浏览器
		所以应该加上浏览器头部，模仿浏览器访问web  res = requests.get(url,headers=send_headers)
		获取资源  res = connect_web(url)
	*BeautifulSoup
		
		将前面获取的数据转换为xml格式：soup = BeautifulSoup(res.text, 'lxml')
		通过该库的方法获取目标标签的数据
		影名   soup.find_all('div', class_='hd')
		评分   soup.find_all('span', class_='rating_num')
		
	*pyinstaller
		
		用于将py文件打包为window可运行文件
	
##
















