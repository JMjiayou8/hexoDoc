---
title: css基础
date: 2019-11-06 09:37:37

tags:
  - css
---

本篇从基础入手

<!--more-->
#### 语法
> 定义

<b>css</b>：层叠样式表,定义如何显示 `HTML` 元素

> 语法
```
选择器 {
  属性1 : 值1;/*分号不可少*/
  属性2 : 值2;
}
```

#### 创建方式

> 外部样式表:`推荐`
```html
<link href="xxx.css" rel="stylesheet"/>
```
> 内部样式表
```html
<style>
  #box{
    width:100px;
  }
</style>
```
> 内联样式
```html
  <div id="box" style=" width:100px;"></div>
```
#### 选择器

> 摘选常见选择器

| 选择器 | 说明 | 备注 |
| - | - | - |
| <b>常用</b> |  |
| elem | 标签名 | p{...}<br>div{...} |
| #id | id属性 | `<div id="box"></div>`<br>#box{...} |
| .class | class属性 | `<div class="box"></div>`<br>.box{...} |
| div,p | 所有`div`元素和`p`元素 | |
| div p | 选择`div`元素内的所有`p`元素 | |
| div>p | 选择所有父级是 `div` 元素的 `p` 元素 | |
| div+p | 选择所有紧接着`div`元素之后的`p`元素 | |
|	div~p|选择`div`元素之后的每一个`p`元素
| <b>属性选择</b> |  |
| [target] | 所有带有target属性元素 | `<p target="xxx"></p>` |
| [target=xxx] | 所有使用target="xxx"的元素 | `<p target="xxx"></p>`|
| [target~=xxx] | 所有使用target包含"xxx"的元素 |`<p target="yyxxxzz"></p>` |
| [target^=xxx] | 所有使用target以"xxx"开头的元素 |`<p target="xxxyyy"></p>` |
| [target$=xxx] | 所有使用target以"xxx"结尾的元素 | `<p target="yyyxxx"></p>`|
| <b>伪类</b> |  |
| :before,:after | 在元素前后插入内容 |
| :link,:visited,:active,:hover | 超链接a元素不同状态 |
| :focus | 具有焦点的输入元素 |
| :disabled,:checked,:required ,:read-only| 设置了特地属性的元素 |

#### 基础实战
> 字体和文本
```html
<p>字体+文本</p>
<style>
p{
  /* 字体 */
  font-size:14px;
  font-weight:bold;  /* 字体加粗 */
  font-style:italic;/* 斜体 */
  font-family:"Times New Roman",Georgia,Serif;
  /* 文本 */
  color:#333;
  text-align:center;/* 文本居中 */
  text-decoration:underline;/* 修饰，下划线 */
  text-transform:uppercase;/* 转成大写*/
  text-indent:50px;/* 文本缩进*/
  line-height:20px;/* 行高 常用来设置垂直居中*/
}
</style>

```

> 盒子模型

![img](/images/box-model.gif?width=100)

总元素的实际宽度=width+padding+border+margin;

设置内外边距方向的顺序为顺时针:`上、右、下、左`
```css
{
  width:100px;
  height:50px;
  padding:5px 10px;/*上下：5px 左右10px*/
  border:1px solid #333;
  margin:10px;/*上下左右：10px */
}

```
此处拓展css3的`box-sizing`属性:
```css
{
  width：500px;
  box-sizing:border-box;/* 500px包含了content,padding,border*/
  box-sizing:content-box;/* 500px包含了contentr*/
}
/* 目前大部分的处理方式是全局设置 box-sizing:border-box; */
```

> 背景

`background`:background-color background-image background-repeat background-attachment background-position
```css
<div class="background">背景</div>
.background{
  width:200px;
  height:200px;
  background:#f1f1f1;/*只定义背景色*/
  background:url('xx') no-repeat center/cover;/*只定义背景图片*/
  background:#f1f1f1 url('xx') no-repeat center/cover;/*定义背景色+背景图片*/
}
```

#### 布局实战
> 显示 [display](https://www.runoob.com/cssref/pr-class-display.html)

了解display前，先对元素分一下类：块元素和内联元素。
1. `块元素`就是独占一行，元素前后都有换行符，常见有div,p,h1-h6等。语法为：`display:block`;
2. `内联元素`就是只有必要的宽度，不会强制换行，常见有span,a等。语法为：`display:inline`;
3. `行内块元素`,内联元素设置宽高无效，一般处理方式是设为行内块元素；块元素想不换行，也可以设为行内块元素。语法为：`display:inline-block`;

> 浮动 [float](https://www.runoob.com/cssref/pr-class-float.html)


> 定位 position

首先了解一下position属性的几个值的概念


> flex布局

超级好用的css3属性，无奈兼容性不佳，后期上手vue项目时可再着重学习。


#### 表格+列表实战
>

#### 表单实战

### 日常开发技巧，调试

浏览器控制台`Elements`页，点选页面元素对应html片段，右侧`Styles`为对应css设置，`Computed`为最终元素对应的css设置。











