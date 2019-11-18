title: es6 实用篇
date: 2019-11-15 09:16:37
tags:
  - js
---

针对性的讲解es6在实际运用中的情况,更详细的讲解见:[ECMAScript 6 入门](https://es6.ruanyifeng.com/#docs/destructuring)

<!-- more -->

### let 和 const 命令

ES6 新增了`let`命令，用来声明变量。它的用法类似于var，但是所声明的变量，只在let命令所在的代码块内有效。

`const`声明一个只读的常量。一旦声明，常量的值就不能改变。

### 解构

```javascript
//es5
let a = 1;
let b = 2;
let c = 3;
//es6
let [a, b, c] = [1, 2, 3];
```

### 模板字符串

```javascript
let str="Jack";
`name is ${str}`
```

### 扩展方法

#### 对象

Object.assign():对象的合并

```javascript
const target = { a: { b: 'c', d: 'e' } }
const source = { a: { b: 'hello' } }
Object.assign(target, source);// { a: { b: 'hello' } }
```

Object.keys()，Object.values()，Object.entries() 
```javascript
let obj = { foo: 'bar', baz: 42 };
Object.keys(obj);// ["foo", "baz"]
Object.values(obj);//["bar", 42]
Object.entries(obj);//[["foo", "baz"],["bar", 42]]
```

#### 函数

参数默认值
```javascript
//es5 常用方式
function log(x, y) {
  y = y || 'World';
  console.log(x, y);
}
//es6 设置默认值
function log(x, y = 'World') {
  console.log(x, y);
}
```

rest 参数
```javascript
Math.max(...[1,2,3,4,5]);//5

function add(...values) {
  let sum = 0;
  console.log(values)
  for (var val of values) {
    sum += val;
  }
  return sum;
}

add(2, 5, 3) // 10
```
箭头函数

```javascript
var f = v => v;

// 等同于
var f = function (v) {
  return v;
};
```

#### 数组

扩展运算符...

```javascript

```

fill()
```javascript
new Array(5).fill(1);//[1, 1, 1, 1, 1] 
``` 

includes()
```javascript
//es6
[1, 2, 3].includes(2);// true
//es5想实现同样效果通常使用indexOf
[1, 2, 3].indexOf(2)>-1;//true
``` 




