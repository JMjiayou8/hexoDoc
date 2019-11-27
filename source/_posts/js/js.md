---
title: js基础
date: 2019-11-07 10:37:37

tags:
  - js
---

着重介绍 js 基础内容

<!--more-->

## 基础

1. `JavaScript` 是 Web 的编程语言。

2. 在 html 文件中引入有两种方式：

- 使用 `script` 标签。浏览器会解释并执行位于 `<script>` 和 `</script>`之间的 JavaScript 代码
- 把脚本保存到外部文件中。外部文件通常包含被多个网页使用的代码。文件扩展名是 .js。在 `script` 标签的 "src" 属性中设置该 .js 文件：

3. JavaScript 使用关键字 `var` 来定义变量， 使用等号来为变量赋值：

```javascript
var num = 1
var text = 'text'
```

### 操作符

| 类型| 实例| 描述|
| - | - | - |
| 赋值运算符 | = += -= \*= /= %=|
| 算术运算符 | + - \* / % ++ -- + -|共提供10个算术运算符，用来完成基本的算术运算
| 比较运算符 | == === != !== > < >= <= |一共提供了8个比较运算符
| 逻辑运算符 | && ！ || | 
| 条件运算符 | ?:| 三目运算符 vari=(condition)?value1:value2 |

### 语句

#### 条件语句

- if 语句 - 只有当指定条件为 true 时，使用该语句来执行代码
- if...else 语句 - 当条件为 true 时执行代码，当条件为 false 时执行其他代码
- if...else if....else 语句- 使用该语句来选择多个代码块之一来执行
- switch 语句 - 使用该语句来选择多个代码块之一来执行

#### 循环语句

- for - 循环代码块一定的次数
- for/in - 循环遍历对象的属性
- while - 当指定的条件为 true 时循环指定的代码块
- do/while - 同样当指定的条件为 true 时循环指定的代码块

## 数据类型

### 基础概念

js 数据基础类型有以下 6 类：

1. 基本类型：String、Number、Boolean、Null、Undefined
2. 引用数据类型：Object。其中包括 Object,Array,Function

ES6 引入了一种新的原始数据类型:Symbol,表示独一无二的值。

### 判断数据类型

1. typeof,简易情况下常用方法

```javascript
typeof 1 //'number'
typeof '1' //'string'
typeof true //'boolean'
typeof undefined //'undefined'
typeof null //'object'
typeof {} //'object'
typeof [] //'object'
typeof function a() {} //'function'
```

2. instanceof 用的不多，就不介绍了。

3. Object.prototype.toString.call():复杂情况下解决方法

```javascript
Object.prototype.toString.call(1) //"[object Number]"
Object.prototype.toString.call('1') //"[object String]"
Object.prototype.toString.call(true) //"[object Boolean]"
Object.prototype.toString.call([]) //"[object Array]"
Object.prototype.toString.call({}) //"[object Object]"
Object.prototype.toString.call(undefined) //"[object Undefined]"
Object.prototype.toString.call() //"[object Undefined]"
Object.prototype.toString.call(function a() {}) //"[object Function]"
```
### 类型详解

#### 数字(Number)

所有数字都是以64位浮点数形式储存，所以，1与1.0是相同的，是同一个数。
```javascript
//返回可以表示的具体的最大值和最小值。
Number.MAX_VALUE // 1.7976931348623157e+308
Number.MIN_VALUE // 5e-324

//默认情况下，JavaScript 内部会自动将八进制、十六进制、二进制转为十进制
0xff // 255
0o377 // 255
```

`NaN`:表示“非数字”（Not a Number）。NaN不等于任何值，包括它本身。
```javascript
NaN === NaN // false
```
`Infinity`:表示“无穷”。
```javascript
//Infinity有正负之分，Infinity表示正的无穷，-Infinity表示负的无穷。
Infinity === -Infinity // false

1 / -0 // -Infinity
-1 / -0 // Infinity
```

> 常用方法

| 方法名     | 描述| 备注 |
| - | - | - |
| toFixed(x) | 把数字转换为字符串，结果的小数点后有指定位数的数字 | num.toFixed(2)     |
| toString() | 把数字转换为字符串，使用指定的基数。默认十进制     |num.toString(2) ;num.toString(8)  
| isNaN()   | 检查某个值是否是数字。 |isNaN(NaN)//true;
| parseInt()<br>parseFloat() | 解析一个字符串并返回一个数值 |
|isFinite()|返回一个布尔值，表示某个值是否为正常的数值。|见下

```javascript
//除了Infinity、-Infinity、NaN和undefined这几个值会返回false，isFinite对于其他的数值都会返回true。
isFinite(Infinity) // false
isFinite(-Infinity) // false
isFinite(NaN) // false
isFinite(undefined) // false
isFinite(null) // true
isFinite(-1) // true
```

#### 字符串（String）

```javascript
var attr = 'jsString'
```

> 常用方法

| 方法名| 描述| 备注|
| - | - | - |
| concat()               | 连接两个或更多字符串，并返回新的字符串。| `var a='x';var b=a.concat('y');<br>a;//"x" b;//"xy"` |
| replace()              |||
| split()                |按照特定分隔符分隔字符串，返回数组|'a,b,c'.split(',');//["a", "b", "c"]|
| substr(startIndex,num) | 从起始索引号提取字符串中指定数目的字符。||
| substring(from,to)     | 提取字符串中介于两个指定下标之间的字符,返回的子串包括 开始 处的字符，但不包括 结束 处的字符。 ||
| trim()                 | 去除字符串两端的空格||
| btoa()<br>atob()       |任意值转为 Base64 编码<br>Base64 编码转为原来的值|不适合非 ASCII 码的字符

```javascript
var string = 'Hello World!';
btoa(string) // "SGVsbG8gV29ybGQh"
atob('SGVsbG8gV29ybGQh') // "Hello World!"

//将非 ASCII 码字符转为 Base64 编码,中间插入一个转码环节
function b64Encode(str) {
  return btoa(encodeURIComponent(str));
}

function b64Decode(str) {
  return decodeURIComponent(atob(str));
}

b64Encode('你好') // "JUU0JUJEJUEwJUU1JUE1JUJE"
b64Decode('JUU0JUJEJUEwJUU1JUE1JUJE') // "你好"
```

#### 布尔(Boolean)

布尔（逻辑）只能有两个值：true 或 false。

```javascript
//使用！！可以快速判断数据布尔值,下面六个值被转为false，其他值都视为true。
!!false //false
!!'' //false
!!0 //false
!!NaN //false
!!null //false
!!undefined //false

//以下几种情况不要误认为false
!!'0' //true
!![]//true
!!{}//true
```

#### 空（Null）、未定义（Undefined)

```javascript
//判断
undefined == null //true
undefined ===null + //false

// 转成数字
null + //0
undefined //NaN
```

#### 引用类型

##### 对象(Object)

```javascript
// 定义
var person={
  firstname:"John",
  lastname:"Doe",
  id:5566
};
//访问对象属性
1. person.firstname
2. person['firstname']
```

##### 数组(Array)

本质上，数组属于一种特殊的对象。typeof运算符会返回数组的类型是object。

```javascript
//常见三种定义数组方式
1. var cars=["Saab","Volvo","BMW"];
2. var cars=new Array("Saab","Volvo","BMW");
3. var cars=new Array();//或 var cars=[];
   cars[0]="Saab";
   cars[1]="Volvo";
   cars[2]="BMW";
```

> 常用方法

| 方法名| 描述| 备注 |
| - | - | - |
| concat()           | 连接两个或更多的数组，并返回结果。||
| sort()             | 排序||
| slice(start,end)   | 返回选定的元素,不会改变原始数组。||
| splice()           | 从数组中添加或删除元素。||
| reverse()          | 倒转数组元素||
| push()<br>pop()    | 向数组的末尾添加一个或更多元素，并返回新的长度。<br>删除数组的最后一个元素并返回删除的元素。 ||
| shift()<br>unshift | 删除并返回数组的第一个元素。<br>向数组的开头添加一个或更多元素，并返回新的长度。|
| join()             | 把数组的所有元素放入一个字符串。||

##### 函数(Function)

```javascript
//函数表达式
var func = function() {
  ...
}
//function 命令
//采用function命令声明函数时，整个函数会像变量声明一样，被提升到代码头部
function func(){
  ...
}
```

> 函数作用域

在 ES5 的规范中，JavaScript 只有两种作用域：一种是全局作用域，变量在整个程序中一直存在，所有地方都可以读取；另一种是函数作用域，变量只在函数内部存在。ES6 又新增了块级作用域，暂不涉及。
函数执行时所在的作用域，是定义时的作用域，而不是调用时所在的作用域。

> 立即调用函数(IIFE)

两种写法都是以圆括号开头,最后的分号都是必须的
```javascript
(function(){ /* code */ }());
// 或者
(function(){ /* code */ })();
```

> eval

eval命令接受一个字符串作为参数，并将这个字符串当作语句执行。
```javascript
eval('var a = 1;');
a; // 1
```
eval的本质是在当前作用域之中，注入代码。由于安全风险和不利于 JavaScript 引擎优化执行速度，所以一般不推荐使用。遇到的两个使用场景如下：
```javascript
// 1. 处理不规范的json字符串。JSON.parse会报错.
var str="{'x':1,'y':2}";
JSON.parse(str);//报错。 
eval('('+str+')');//{x: 1, y: 2}

//2. 不推荐，但也是一种解决方案吧。
var arr=[1,2,3,4,5];
eval(arr.join('+'));//15
```

#### 全局对象

除了基础的 6 种数据类型，还有几类额外的全局对象类型，大致了解一下。

##### Date

日期对象用于处理日期和时间。

```javascript
var date = new Date()
typeof date //'object'
Object.prototype.toString.call(date) //"[object Date]"
```

摘选常用的方法讲解，全部清单见：[链接~](https://www.runoob.com/jsref/jsref-obj-date.html) ; get 方法都一一对应 set 方法，不赘述。

| 方法名        | 描述                               | 备注                      |
| ------------- | ---------------------------------- | ------------------------- |
| getFullYear() | 以四位数字返回年份                 | date.getFullYear();//2019 |
| getMonth()    | 返回月份 (0 ~ 11)                  | date.getMonth();          |
| getDate()     | 返回一个月中的某一天 (1 ~ 31)      | date.getDate();           |
| getDay()      | 返回一周中的某一天 (0 ~ 6)         | date.getDay();            |
| getHours()    | 返回小时 (0 ~ 23)                  | date.getHours();          |
| getMinutes()  | 返回分钟 (0 ~ 59)                  | date.getMinutes();        |
| getSeconds()  | 返回秒数 (0 ~ 59)                  | date.getSeconds();        |
| getTime()     | 返回 1970 年 1 月 1 日至今的毫秒数 | date.getTime();或者+date; |

##### Math

Math 对象用于执行数学任务。Math 对象并不像 Date 和 String 那样是对象的类，因此没有构造函数 Math()。

```javascript
var math = Math
typeof math //'object'
Object.prototype.toString.call(math) //"[object Math]"
```

摘选常用的方法讲解，全部清单见：[链接~](https://www.runoob.com/jsref/jsref-obj-math.html)

| 方法名           | 描述                      | 备注                                           |
| ---------------- | ------------------------- | ---------------------------------------------- |
| max(x,y,z,...,n) | 求最大值                  | Math.max(1,2,7,3); //7                         |
| min(x,y,z,...,n) | 求最小值                  | Math.min(1,2,7,3); //1                         |
| random()         | 返回 0 ~ 1 之间的随机数。 | Math.random();                                 |
| abs(x)           | 返回 x 的绝对值。         | Math.abs(-1);//1                               |
| ceil(x)          | 对 x 进行向上取整。       | Math.ceil(4.1);//5<br>Math.ceil(4.6);//5       |
| floor(x)         | 对 x 进行向下取整。       | Math.floor(4.1);//4<br>Math.floor(4.6);//4     |
| round(x)         | 四舍五入                  | Math.round(4.1);//4<br>Math.round(4.6);//5<br> |

### 类型转换

> Number():使用Number函数，可以将任意类型的值转化成数值。

除此之外，一般还会使用`parseFloat()`,`parseInt()`,`+`完成类似功能，但严谨度不太一样。下面列举具体的情况:

| 转换前 | Number() | parseFloat() | parseInt() | +val
| - | - | - | - | - |
| '123' | 123 | 123 | 123 | 123 |
| '123a' | NaN | 123 | 123 | NaN |
| '' | 0 | NaN | NaN | 0 |
| true | 1 | NaN | NaN | 1 |
| false | 0 | NaN | NaN | 0 |
| undefined | NaN | NaN | NaN | NaN |
| null | 0 | NaN | NaN | 0 |
| [] | 0 | NaN | NaN | 0 |
| [2] | 2 | 2 | 2 | 2 |
| [2,3] | NaN | 2 | 2 | NaN |
| {} | NaN | NaN | NaN | NaN |

> String():使用String函数，可以将任意类型的值转化成字符串
| 转换前 | Number() | +'' | 
| - | - | - |
| 'abc'|'abc'|'abc'
| 123|'123'|'123'
| true|'true'|'true'
| null|'null'|'null'
| undefined|'undefined'|'undefined'
| []|''|''
| [1,2]|"1,2"|'1,2'
| [{'x':1}]|"[object Object]"|"[object Object]"
| {'x':1}|"[object Object]"|"[object Object]"


## 浏览器对象

Window 对象表示浏览器中打开的窗口。本篇结合日常使用频率，介绍常用属性和方法，更多[戳这里~](https://www.runoob.com/jsref/obj-window.html)

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
var w =
  window.innerWidth ||
  document.documentElement.clientWidth ||
  document.body.clientWidth

var h =
  window.innerHeight ||
  document.documentElement.clientHeight ||
  document.body.clientHeight
```

### 浏览器窗口操作

- window.open() - 打开新窗口
- window.close() - 关闭当前窗口
- window.moveTo() - 移动当前窗口
- window.resizeTo() - 调整当前窗口的尺寸

### 浏览器 URL

window.location 对象用于获得当前页面的地址 (URL)，并把浏览器重定向到新的页面。

- location.hostname 返回 web 主机的域名
- location.pathname 返回当前页面的路径和文件名
- location.port 返回 web 主机的端口 （80 或 443）
- location.protocol 返回所使用的 web 协议（http: 或 https:）

### 浏览器历史

- history.back() - 与在浏览器点击后退按钮相同
- history.forward() - 与在浏览器中点击向前按钮相同

### 浏览器存储对象

localStorage

用于长久保存整个网站的数据，保存的数据没有过期时间，直到手动去删除。属性是只读的。localStorage 只支持 string 类型的存储。

```javascript
localStorage.setItem('key', 'value')
var lastname = localStorage.getItem('key')
localStorage.removeItem('key')
localStorage.clear()
```

sessionStorage

用于临时保存同一窗口(或标签页)的数据，在关闭窗口或标签页之后将会删除这些数据。

```javascript
sessionStorage.setItem('key', 'value')
var lastname = sessionStorage.getItem('key')
sessionStorage.removeItem('key')
sessionStorage.clear()
```

### 浏览器弹框

警告框

```javascript
alert('你好，我是一个警告框！')
```

确认框

```javascript
window.confirm('你好，我是一个确认框！')
```

提示框

```javascript
var text = window.prompt('你好，我是一个确认框！', '默认值')
```

### 计时

setInterval() - 间隔指定的毫秒数不停地执行指定的代码。

```javascript
//每三秒弹出 "hello" ：
var t = setInterval(function() {
  alert('Hello')
}, 3000)
//清除定时器
clearInterval(t)
```

setTimeout() - 在指定的毫秒数后执行指定代码。

```javascript
//三秒后弹出 "hello" ：
var t = setTimeout(function() {
  alert('Hello')
}, 3000)
//清除定时器
clearTimeout(t)
```


## DOM

## 高阶

### 闭包
JavaScript 有两种作用域：全局作用域和函数作用域。函数内部可以直接读取全局变量。但是，函数外部无法读取函数内部声明的变量。
```javascript
function f1() {
  var n = 123;
  function f2() {
    console.log(n);
  }
  return f2;
}

var result = f1();
result(); // 999

//函数f2就是闭包，即能够读取其他函数内部变量的函数。
```
可以把闭包简单理解成“定义在一个函数内部的函数”,可以“记住”诞生的环境
闭包的最大用处有两个，一个是可以读取函数内部的变量，另一个就是让这些变量始终保持在内存中，即闭包可以使得它诞生环境一直存在。


## 日常开发技巧，调试

1. 使用 `window.alert()` 弹出警告框。
2. 使用 `console.log()` 写入到浏览器的控制台。
3. 使用`debugger`进行调试断点调试。

简单的 js 直接在浏览器控制台运行，复杂一点的个人习惯新建 js 文件，再用 node 环境运行。
