---
title: jquery基础
date: 2019-11-08 10:37:37

tags:
  - jquery
---

jquery基础

<!--more-->

### 基础

可以到github上下载对应版本的包：[戳这里~](https://github.com/jquery/jquery/releases)
下载后，html中引入dist文件夹中的jquery.js(或jquery.min.js)
```html
<script src="../dist/jquery.min.js"></script>
```
关键字`$`

### 选择器

和之前了解过css的选择器可以联系记忆,下面摘选常见选择器

| 选择器 | 说明 | 备注 |
| - | - | - |
| <b>常用</b> |  |
| elem | 标签名 | $('div') |
| #id | id属性 | $('#box') |
| .class | class属性 | $('.box') |
| div,p | 所有`div`元素和`p`元素 | $('div,p')|
| div p | 选择`div`元素内的所有`p`元素 |$('div p') |
| div>p | 选择所有父级是 `div` 元素的 `p` 元素 |$('div>p') |
| div+p | 选择所有紧接着`div`元素之后的`p`元素 |$('div+p') |
|	div~p|选择`div`元素之后的每一个`p`元素|$('div~p')
| <b>属性选择</b> |  |
| [target] | 所有带有target属性元素 | $('div[target]') |
| [target=xxx] | 所有使用target="xxx"的元素 |  $("div[target='xxx']")|
| [target!=xxx] | 所有使用target不等于"xxx"的元素 | $("div[target！='xxx']") |
| [target^=xxx] | 所有使用target以"xxx"开头的元素 | $("div[target^='xxx']") |
| [target$=xxx] | 所有使用target以"xxx"结尾的元素 |  $("div[target$='xxx']")|
| [target*=xxx] | 所有使用target包含"xxx"的元素 |  $("div[target*='xxx']")|
| <b>计数类</b> |  |
| :even<br>:odd | 索引值为偶数/计数的元素<br>从 0 开始计数 |$("tr:even")<br>$("tr:odd")
|:eq(i)<br>:gt(i)<br>:lt(i)|匹配一个<br>等于/大于/小于给定索引值的元素,<br>从 0 开始计数|$("tr:eq(1)")<br>$("tr:gt(1)")<br>$("tr:lt(1)")
| <b>子元素</b> |  |
| :nth-child | 匹配其父元素下的第N个子元素<br>从 1 开始计数 |$("ul li:nth-child(2)");<br>匹配ul下第2个li元素
|:first-child<br>:last-child|匹配<br>第一个/最后一个元素|$("ul li:first-child")<br>$("ul li:last-child")
| <b>元素状态</b> |  |
| :hidden<br>:visible|匹配所有不可见/可见元素 |$("tr:hidden")<br>$("tr:visible") |
| :disabled<br>:checked<br>:selected<br>|表单元素 |$("input:disabled")<br>$("input:checked")<br>$("select option:selected") |
| <b>元素类型</b> |  |
|:input|匹配所有 input, textarea, select 和 button 元素|$(":input")
|:button|所有按钮|$(":button")<br>`<input type="button" />`或<br>`<button></button>`
|:radio<br>:checkbox<br>:submit<br>:reset|所有单选按钮<br>所有复选框<br>所有提交按钮<br>所有重置按钮|$(":radio")`<input type="radio" />` <br>$(":checkbox")`<input type="checkbox" />` <br>$(":submit")`<input type="submit" />` <br>$(":reset")`<input type="reset" />` 

### 方法
| 方法 | 说明 | 备注 |
| - | - | - |
| <b>自定义属性</b> |  |
| attr(name,val) | 获取/设置属性 | $("img").attr("src");<br>$("img").attr("src",'xxx.png'); |
| removeAttr(name) | 删除属性 | $("img").removeAttr("src"); |
| <b>固有属性</b> |  |
| prop(name,val) | 获取/设置属性 | $("input[type='checkbox']").prop("checked");<br>$("input[type='checkbox']").prop("checked", true); |
| <b>内容、值</b> |  |
| html(val) | 匹配/设置元素的html内容 | $('#box').html()<br>$('#box').html('html') |
| text(val) | 匹配/设置元素的内容 | $('#box').text()<br>$('#box').text('html') |
| val(val) | 匹配/设置元素的值| $("input").val();<br>$("input").val('val'); |
| <b>class样式类</b> |  |
| hasClass(name) | 是否含有某个特定的类 |$('#box').hasClass("active")
| addClass(name)<br>removeClass(name)|新增/删除样式类|$('#box').addClass("active")<br>$('#box').removeClass("active")
| toggleClass(name)|如果存在（不存在）就删除（添加）一个类。|$('#box').toggleClass("active")
| <b>筛选</b> |  |
| find() | 与指定表达式匹配的元素 |$("p").find("span")<br>与$("p span")相同
| parent()<br> parents() | 父元素 |
| prev()<br> next() <br>siblings()| 邻居元素 |
| eq(index) | 获取第N个元素,从0开始 |$("p").eq(1)
| first()<br>last()|第一个/最后一个元素|$('li').first()<br>$('li').last()
| <b>样式</b> |  |
| css(key,val) | 设置样式 |$("p").css("color");<br>$("p").css("color","#333");









