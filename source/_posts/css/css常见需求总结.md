---
title: css常见需求总结
date: 2019-11-06 10:37:37

tags:
  - css
---

本篇根据日常管理系统遇到比较多的情况入手，介绍常见的处理方法

<!--more-->
#### 字体

> 常规

```css
span{
  font-weight:bolder;/*字体加粗*/
  font-style: italic;/*字体倾斜*/
}
em,i{
   font-style: normal;/*去除字体倾斜*/
}
```
> 超链接

```css
a{
  cursor:pointer;/*鼠标移上去有小手*/
  text-decoration:underline;/*下划线装饰*/
  text-decoration:none;/*去除下划线装饰*/
}
a:hover{
  opacity:.8;/*悬浮透明效果*/
}
```

> 多余展示省略号
```css
p{
  /*需要固定宽度*/
  width: 50px;
  /* 下面三句是固定搭配，缺一不可*/
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}
```











