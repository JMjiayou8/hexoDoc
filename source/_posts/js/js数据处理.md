---
title: js数据类型专题
date: 2019-11-07 11:37:37

tags:
  - js
---
本篇着重讲解js数据类型及相关内置函数
<!--more-->

### 基础概念

js数据基础类型有以下6类：

1. 基本类型：String、Number、Boolean、Null、Undefined
2. 引用数据类型：Object。其中包括Object,Array,Function

ES6引入了一种新的原始数据类型:Symbol,表示独一无二的值。

###  判断数据类型

1. typeof,简易情况下常用方法
```javascript
typeof 1;//'number'
typeof '1';//'string'
typeof true;//'boolean'
typeof undefined;//'undefined'
typeof null;//'object'
typeof {};//'object'
typeof [];//'object'
typeof function a(){};//'function'
```
2. instanceof 用的不多，就不介绍了。
3. Object.prototype.toString.call():复杂情况下解决方法
``` javascript
Object.prototype.toString.call(1); //"[object Number]"
Object.prototype.toString.call('1'); //"[object String]"
Object.prototype.toString.call(true); //"[object Boolean]"
Object.prototype.toString.call([]); //"[object Array]"
Object.prototype.toString.call({}); //"[object Object]"
Object.prototype.toString.call(undefined); //"[object Undefined]"
Object.prototype.toString.call(); //"[object Undefined]"
Object.prototype.toString.call(function a(){}); //"[object Function]"
```
### 数字(Number)

```javascript
var num1=1;
var num2=1.5;
```
> 常用方法

| 方法名 | 描述 | 备注 |
| - | - | - |
| toFixed(x) | 把数字转换为字符串，结果的小数点后有指定位数的数字 |  |
| toString()| 把数字转换为字符串，使用指定的基数。默认十进制| 

### 字符串（String）

```javascript
var attr="jsString";
```

> 常用方法

| 方法名 | 描述 | 备注 |
| - | - | - |
| concat() | 连接两个或更多字符串，并返回新的字符串。 | `var a='x';var b=a.concat('y');<br>a;//"x" b;//"xy"` |
| replace() |  |  |
| slice() |  |  |
| split() |  |  |
| substr() |  |  |
| substring() |  |  |
| trim() |  |  |
| toString() |  |  |

### 布尔(Boolean)

布尔（逻辑）只能有两个值：true 或 false。

```javascript
var attr=true;
```


### 空（Null）、未定义（Undefined)
```javascript
var attr=null;//可以通过将变量的值设置为 null 来清空变量
```

### 引用类型

#### 对象(Object)

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

#### 数组(Array)
```javascript
//常见三种定义数组方式
1. var cars=["Saab","Volvo","BMW"];
2. var cars=new Array("Saab","Volvo","BMW");
3. var cars=new Array();//或 var cars=[];
   cars[0]="Saab";
   cars[1]="Volvo";
   cars[2]="BMW";
```

#### 函数(Function)
```javascript
var func=function(){
  };
```

### 全局对象

除了基础的6种数据类型，还有几类额外的全局对象类型，大致了解一下。

#### Date

日期对象用于处理日期和时间。
```javascript
var date=new Date();
typeof date;//'object'
Object.prototype.toString.call(date);//"[object Date]"
```
摘选常用的方法讲解，全部清单见：[链接~](https://www.runoob.com/jsref/jsref-obj-date.html) ; get方法都一一对应set方法，不赘述。

| 方法名 | 描述 | 备注 |
| - | - | - |
| getFullYear() | 以四位数字返回年份 | date.getFullYear();//2019 |
| getMonth() | 返回月份 (0 ~ 11) | date.getMonth();|
| getDate() | 返回一个月中的某一天 (1 ~ 31) | date.getDate();|
| getDay() | 返回一周中的某一天 (0 ~ 6) | date.getDay();|
| getHours() | 返回小时 (0 ~ 23) | date.getHours();|
| getMinutes() | 返回分钟 (0 ~ 59) | date.getMinutes();|
| getSeconds() | 返回秒数 (0 ~ 59) | date.getSeconds();|
| getTime()| 返回 1970 年 1 月 1 日至今的毫秒数| date.getTime();或者+date;

#### Math

Math 对象用于执行数学任务。Math 对象并不像 Date 和 String 那样是对象的类，因此没有构造函数 Math()。
```javascript
var math=Math;
typeof math;//'object'
Object.prototype.toString.call(math);//"[object Math]"
```
摘选常用的方法讲解，全部清单见：[链接~](https://www.runoob.com/jsref/jsref-obj-math.html)

| 方法名 | 描述 | 备注 |
| - | - | - |
| max(x,y,z,...,n) | 求最大值 | Math.max(1,2,7,3); //7|
| min(x,y,z,...,n) | 求最小值 | Math.min(1,2,7,3); //1 |
| random() | 返回 0 ~ 1 之间的随机数。 | Math.random(); |
| abs(x) | 返回 x 的绝对值。 | Math.abs(-1);//1 |
| ceil(x)|对 x 进行向上取整。|Math.ceil(4.1);//5<br>Math.ceil(4.6);//5
| floor(x)|对 x 进行向下取整。|Math.floor(4.1);//4<br>Math.floor(4.6);//4
| round(x)|四舍五入|Math.round(4.1);//4<br>Math.round(4.6);//5<br>








