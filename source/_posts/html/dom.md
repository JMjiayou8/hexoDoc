---
title: DOM操作
date: 2019-11-08 14:37:37

tags:
  - html
  - js
---
本篇讲解html dom基础知识，以及js原生操作dom和jquery操作的对比
<!--more-->

### 基础

DOM (Document Object Model):文档对象模型，是 HTML 和 XML 文档的编程接口。HTML DOM 定义了访问和操作 HTML 文档的标准方法。DOM 以树结构表达 HTML 文档。

![img](/images/htmltree.gif?width=100)

### 节点

在 HTML DOM (Document Object Model) 中 , 每一个元素都是 节点:
- 文档是一个文档节点。
- 所有的HTML元素都是元素节点。
- 所有 HTML 属性都是属性节点。
- 文本插入到 HTML 元素是文本节点。are text nodes。
- 注释是注释节点。

Document 对象是 HTML 文档的根节点。Document 对象使我们可以从脚本中对 HTML 页面中的所有元素进行访问。

### js和jquery操作

```javascript
<div id="box" attr1 onclick="clickHandle();"></div>
var elem=document.getElementById('box');
```

| 功能 | js | jquery |
| - | - | - |
|<b>获取元素</b>|
| 获取指定id的元素 | document.getElementById('box') | $('#box') |
| 获取指定class的元素 | document.getElementsByClassName('box') | $('.box) |
|<b>样式</b>||
| 获取指定样式 | getComputedStyle(elem).height | $('#box').css('height') |
| 设置指定样式 | elem.style.height='50px' | $('#box').css('height','50px') |
|<b>属性</b>|
| 获取指定属性 | elem.getAttribute('attr1') | $('#box').attr('attr1') |
| 设置指定属性 | elem.setAttribute('attr1','attr1Value') | $('#box').attr('attr1','attr1Value') |
|<b>事件</b>|
| 绑定事件 | functin clickHandle(){}<br>elem.onclick=clickHandle;<br>elem.addEventListener("click",clickHandle,false); | $('#box','click',clickHandle) |






