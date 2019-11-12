---
title: js浏览器相关
date: 2019-11-07 11:37:37

tags:
  - js
---

Window 对象表示浏览器中打开的窗口。本篇结合日常使用频率，介绍常用属性和方法，更多[戳这里~](https://www.runoob.com/jsref/obj-window.html)

<!--more-->

### 浏览器尺寸

1. Internet Explorer、Chrome、Firefox、Opera 以及 Safari
- window.innerHeight - 浏览器窗口的内部高度(包括滚动条)
- window.innerWidth - 浏览器窗口的内部宽度(包括滚动条)
2. Internet Explorer 8、7、6、5
- document.documentElement.clientHeight
- document.documentElement.clientWidth
3. 其余
document.body.clientHeight
document.body.clientWidth

实用的 JavaScript 方案（涵盖所有浏览器）
```javascript
var w=window.innerWidth
|| document.documentElement.clientWidth
|| document.body.clientWidth;

var h=window.innerHeight
|| document.documentElement.clientHeight
|| document.body.clientHeight;
```

### 浏览器窗口操作

- window.open() - 打开新窗口
- window.close() - 关闭当前窗口
- window.moveTo() - 移动当前窗口
- window.resizeTo() - 调整当前窗口的尺寸

### 浏览器URL

window.location 对象用于获得当前页面的地址 (URL)，并把浏览器重定向到新的页面。

- location.hostname 返回 web 主机的域名
- location.pathname 返回当前页面的路径和文件名
- location.port 返回 web 主机的端口 （80 或 443）
- location.protocol 返回所使用的 web 协议（http: 或 https:）

### 浏览器历史

- history.back() - 与在浏览器点击后退按钮相同
- history.forward() - 与在浏览器中点击向前按钮相同

### 浏览器存储对象

- localStorage

用于长久保存整个网站的数据，保存的数据没有过期时间，直到手动去删除。属性是只读的。localStorage 只支持 string 类型的存储。

```javascript
localStorage.setItem("key", "value");
var lastname = localStorage.getItem("key");
localStorage.removeItem("key");
localStorage.clear();
```
- sessionStorage

用于临时保存同一窗口(或标签页)的数据，在关闭窗口或标签页之后将会删除这些数据。

```javascript
sessionStorage.setItem("key", "value");
var lastname = sessionStorage.getItem("key");
sessionStorage.removeItem("key");
sessionStorage.clear();
```

### 浏览器弹框

- 警告框

```javascript
alert("你好，我是一个警告框！");
```
- 确认框

```javascript
window.confirm("你好，我是一个确认框！");
```
- 提示框

```javascript
var text=window.prompt("你好，我是一个确认框！","默认值");
```

### 计时

- setInterval() - 间隔指定的毫秒数不停地执行指定的代码。

```javascript
//每三秒弹出 "hello" ：
var t=setInterval(function(){
  alert("Hello")
},3000);
//清除定时器
clearInterval(t);
```

- setTimeout() - 在指定的毫秒数后执行指定代码。
```javascript
//三秒后弹出 "hello" ：
var t=setTimeout(function(){
  alert("Hello")
},3000);
//清除定时器
clearTimeout(t);
```




