---
title: html+css
published: 2025-10-19
description: ''
image: ''
tags: []
category: '前端'
draft: false 
lang: 'zh-CN'
---



### 标签

<b>/<strong>		加粗(右侧有强调语义)

<u>/<ins>		下划线

<i>/<em>		倾斜

<s>/<del>		删除线

<a>		超链接			

</video>		视频

</img>		图片

</p>		段落

</br>		换行	

`<div>`：

- 一行只显示一个（独占一行）
- 宽度默认是父元素的宽度，高度默认由内容撑开
- 可以设置宽高（width、height）

<span>：

- 一行可以显示多个
- 宽度和高度默认由内容撑开
- 不可以设置宽高（width、height）

​			

### 字符实体

&nbsp		空格

&lt		小于

&gt		大于

### css属性

line-height		行高

text-indent		首行缩进

href		指定资源访问的url

target	

​	_self		默认值在当前页面打开

​	_blank		在空白页面打开

### css引入方式

行内样式	在标签内使用style属性，属性值是css属性键值对。

内部样式	定义<style>标签，在标签内部定义css样式。

外部样式	定义<link>标签，通过href属性引入外部css文件

### 颜色表示方法

关键字	英文单词

rgb	rgb(r,g,b)

rgba	rgba()

十六进制	#rrggbb

### 选择器

元素选择器	h1{}

类选择器	.cls{}

id选择器	#hid{}

### 路径表示

绝对路径

​	绝对网络路径

​	绝对磁盘路径

相对路径

​	./	当前目录(可以省略)

​	../	上一级目录

### 盒子模型

盒子模型组成：内容区域（content）、内边距区域（padding）、边框区域（border）、外边距区域（margin）-不属于盒子大小。



#### 表单标签

</form>

属性 

​	action 提交时发送url

​	 method 	发送表单方式 get post

- `GET`：表单数据是拼接在url后面的，?username=Tom&age=12，url中能携带的表单数据大小是有限制的。

- `POST`： 表单数据是在请求体（消息体）中携带的，大小没有限制。

    表单项标签: 不同类型的input元素、下拉列表、文本域等。

    - `input`: 定义表单项，通过type属性控制输入形式

    - `select`: 定义下拉列表

    - `textarea`: 定义文本域

        