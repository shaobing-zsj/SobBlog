---
title: js
published: 2025-10-19
description: 
image: ''
tags: []
category: '前端'
draft: false 
lang: 'zh-CN'
---



#### JS引入方式

内部脚本，将JS代码定义在HTML页面中

- JavaScript代码必须位于<script></script>标签之间
- 在HTML文档中，可以在任意地方，放置任意数量的<script></script>
- 一般会把脚本置于<body>元素的底部，可改善显示速度



外部脚本， 将JS代码定义在外部 JS文件中，然后引入到 HTML页面中

- 外部JS文件中，只包含JS代码，不包含<script>标签
- 引入外部js的<script>标签，必须是双标签

JS书写规范：

- 结束符：每行js代码，结尾以分号结尾，而结尾的分号可有可无。（建议在一个项目中保持一致，要么全部都加，要么全部都不加）
- 注释：单行注释，多行注解的写法， 与java中一致。

常量/变量

- js是弱类型语言,变量可以存放不同类型的值

变量名规则

- 组成字符可以是任何字母、数字、下划线（_）或美元符号（$），且数字不能开头
- 变量名严格区分大小写，如：name和Name是不同的变量
- 不能使用关键字作为变量名，如：let、if、for等

输出语句

- window.alert
- document.write
- console.log

常量 const 不能在赋值

声明变量

​	let a = 0;

数据类型

- number		NaN 是数字
- string
- boolean
- null
- undefined

模板字符串

- 对于字符串类型的数据，除了可以使用双引号（"..."）、单引号（'...'）以外，还可以使用反引号 （``）。 而使用反引号引起来的字符串，也称为 **模板字符串**。

- ex:

    1. console.log('大家好, 我是新入职的' + name + ', 今年' + age + '岁了, 请多多关照'); //原始方式 , 手动拼接字符串   

    2. console.log(`大家好, 我是新入职的${name}, 今年${age}岁了, 请多多关照`); //使用模板字符串方式拼接字符串

        使用${	}将变量名括起来

函数

```JavaScript
function 函数名(参数1,参数2..){
    要执行的代码
}
```

​	像 java 一样可以使用lambda表达式

自定义对象

```JavaScript
let 对象名 = {
    属性名1: 属性值1,
    属性名2: 属性值2,
    属性名3: 属性值3,
    方法名称: function(形参列表){}
};
```

​	使用 . 调用属性和方法

​	写方法可以把 function省略掉

JSON

​	JSON对象：**J**ava**S**cript **O**bject **N**otation，JavaScript对象标记法。JSON是通过	JavaScript标记法书写的文本。其格式如下：

```JavaScript
{
    "key":value,
    "key":value,
    "key":value
}
```

​	其中，**key必须使用引号并且是双引号标记，value可以是任意数据类型。**

​	JSON.stringify(...)：作用就是将js对象，转换为json格式的字符串。

​	JSON.parse(...)：作用就是将json格式的字符串，转为js对象。

循环	和java一样

JS DOM

​	Document Object Model 文档对象模型。也就是 JavaScript 将 HTML 文档	的各	个组成部分封装为对象。

- Document：整个文档对象
- Element：元素对象
- Attribute：属性对象
- Text：文本对象
- Comment：注释对象

我们可以通过如下两种方式来获取DOM元素。

1. 根据CSS选择器来获取DOM元素，获取到匹配到的第一个元素：`document.querySelector('``CSS选择器``');`
2. 根据CSS选择器来获取DOM元素，获取匹配到的所有元素：document.querySelectorAll('CSS选择器');

注意：获取到的所有元素，会封装到一个NodeList节点集合中，是一个伪数组（有长度、有索引的数组，但没有push、pop等数组方法）

DOM操作步骤:

- 获取DOM元素对象
- 操作DOM对象的属性或方法 (查阅文档)

JS事件监听

​	事件源.addEventListener('事件类型', 要执行的函数);

在上述的语法中包含三个要素: 

- 事件源: 哪个dom元素触发了事件, 要获取dom元素
- 事件类型: 用什么方式触发, 比如: 鼠标单击 click, 鼠标经过 mouseover
- 要执行的函数: 要做什么事

confirm函数

​	在 JavaScript 中，`confirm()` 是一个浏览器原生提供的全局函数，用于弹出一个带“确定”和“取消”按钮的对话框，并返回一个布尔值

事件类型

click	单击

mouseenter	鼠标移入

mouseleave	鼠标移出

keydown	键盘按下

keyup	键盘抬起

focus	获得焦点

blur	失去焦点

input	输入

submit	提交
