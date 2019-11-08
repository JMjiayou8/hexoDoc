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






