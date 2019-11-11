---
title: html基础
date: 2019-11-05 10:37:37

tags:
  - html
---
本篇从基础和实战两方面入手
<!--more-->
### 基础
<b>HTML</b>:超文本标记语言,是用来创建网页的标准标记语言。文件后缀`.html`

目前普遍存在的问题是复制粘贴后dom结构混乱,以及没有语义化使用标签，即用合理、正确的标签来展示内容，而不是满屏的div。

#### 标签
html文件通俗一点讲就是由标签组成的文档，所以基础就是要熟悉常见的标签：[清单戳这里~](https://www.runoob.com/tags/ref-byfunc.html)
标签就是由尖括号包围的关键词，一般成对出现，如`<div>...</div>`，内容在两个标签中间。也有自闭合标签，内容一般以属性形式赋值，如`<input value="xxx"/>`

我根据日常使用的频率，摘选常见的标签讲解一下

| 标签名 | 描述 | 备注 | 
| - | - | - |
|<b>基础</b>|
|`<!DOCTYPE>`|定义文档类型|html文件中第一行，严格意义上不是html标签，是用来告知浏览器页面使用了哪种HTML版本。
|`html`、`head`、`body`||
|`script`、`link`、`style`|定义外部资源、内联资源| 
|`div`|块元素|单独一行,会换行
|`span`|行内元素|不会换行
|`h1`-`h6`|标题|
|`p`|段落|
|`a`|超链接|`<a href="xxx"></a>`
|`ul`、`ol`、`li`|列表|`<ul><li></li></ul>`<br>`<ol><li></li></ol>`
|<b>表单</b>|
|`form`|表单|
|`input`、`select`、`textarea`|表单元素|输入框、下拉框、多行文本框
|`button`|按钮|`<button>按钮</button>`
|<b>表格</b>|
|`table`|表格|
|`thead`、`tbody`、`tr`、`th`、`td`|表格|
|<b>多媒体</b>|
|`img`|图片|`<img src="xxx" alt="yyy"/>` 
|`video`|视频|

#### 属性
| 属性名 | 描述 | 备注 |
| - | - | - |
| id | 元素的唯一id | 唯一性 |
| class | 元素的类名（classname） |  |
| title | 元素的额外信息 | 鼠标悬浮可见  |
| name | |
| data-* | 存储页面的自定义数据 |
| style| 元素的行内样式 |
| src|  |
| disabled、readonly|  |

#### 事件
| 事件名 | 描述 | 备注 |
| - | - | - |
| onload | 当文档加载时运行脚本 | |
| onclick、ondblclick | 元素单击、双击 |  |
| onfocus、onblur | 元素获取、失去焦点|   |
| onkeydown、onkeypress、onkeyup | 键盘事件|

### 实战

1. 新建一个html文件test.html
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>test页面</title>
  <link href="xxx.css" rel="stylesheet"/>
  <style>
    div{
      color:#000;
    }
  </style>
</head>
<body>
  <div>
    test页面
  </div>
  <script src="xxx.js"></script>
  <script>
    ...
  </script>
</body>
</html>
```







