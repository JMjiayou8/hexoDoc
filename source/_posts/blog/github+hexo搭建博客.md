---
title: github+hexo搭建博客
date: 2019-03-08 15:58:00

tags:
  - 个人
---

平时工作学习会随手记很多东西，也在一些线上平台整理发布过，但零零散散的实在不成系统，就想着搞个人博客。去年 8 月份开始，两个多月吧，博客前台展示，管理系统，服务端。摸摸索索的搞了一个，但是实在审美有限，总觉得不好看。加上后期服务器到期并且没有闲钱续租，所以就半途而废了 🤷‍♀。
最近又开始闲了，有想着优化一下，但是设计是过不去的一道坎。然后就那天看[羡辙小姐姐的个人主页](http://zhangwenli.com/)，奇怪项目名称是 `xxx.github.io`。就去稍稍搜索研究了一下。然后就说干就干了哈。

<!--more-->

#### 准备工作

- 注册[github](https://github.com)账号
- 新建一个项目，右上角`+`号下拉选择`New repository`
- 项目名称规范：`username.github.io` （username 指注册时的用户名哦）
- 进入项目链接后右上角有`setting`,页面下滑找到`GitHub Pages`这个部分；如果出现`Your site is published at https://xxx.github.io/`就代表创建成功啦。下面有一个`choose theme`按钮,就可以去选择自己喜欢的主题啦。
- 选择主题后会默认生成一个主题的`readme.md`文件。也就是博客默认进入的页面。当然，如果你在根目录新建一个 index.html，那默认页面就变成 index.html 啦。剩下的就和平常做项目一样啦。写完代码 push 到 github 上就可以看到啦。

#### 引入 hexo

- 实话说并不知道有这样现成的博客系统，是我搜索 github 建博客的时候那个博主介绍的。既然有便捷的工具那就尝试一下啦。
- 需要 nodejs 和 git 的环境，这是基础，就不赘述了。

```
mkdir hexoPro
cd hexoPro
npm install hexo-cli -g
hexo init
npm install
hexo g
hexo s

//输入完之后就可以本地预览效果了 http://localhost:4000
```

#### hexo 部署到 github

- 打开根目录下的`_config.yml`文件，在最底部加上以下代码

```
//repository的name填自己的用户名哦
deploy:
  type: git
  repository: https://github.com/name/name.github.io.git
  branch: master
```

- 继续输入以下命令

```
npm install hexo-deployer-git --save
cd ~/.ssh
ls #此时会显示一些文件
mkdir key_backup
cp id_rsa* key_backup
rm id_rsa* #以上三步为备份和移除原来的SSH key设置
ssh-keygen -t rsa -C "邮件地址@youremail.com" #生成新的key文件,邮箱地址填你的Github地址
#Enter file in which to save the key (/Users/your_user_directory/.ssh/id_rsa):<回车就好，当然也可以输入自己喜欢的名字>
#接下来会让你输入密码，然后会确认一遍，如果是Linux可能是隐形字
#上面的操作都成功之后会出现一个图，画的很拙劣，是表示OK了
```

#### hexo 使用

- [文档](http://theme-next.iissnan.com/getting-started.html)

- 文章会自动生成目录呢，棒棒哒 💯

> 点击爱心效果

1. 在/themes/next/source/js/src 下新建文件 clicklove.js

```
!function (e, t, a) { function n () { c(".heart{width: 10px;height: 10px;position: fixed;background: #f00;transform: rotate(45deg);-webkit-transform: rotate(45deg);-moz-transform: rotate(45deg);}.heart:after,.heart:before{content: '';width: inherit;height: inherit;background: inherit;border-radius: 50%;-webkit-border-radius: 50%;-moz-border-radius: 50%;position: fixed;}.heart:after{top: -5px;}.heart:before{left: -5px;}"), o(), r() } function r () { for (var e = 0; e < d.length; e++)d[e].alpha <= 0 ? (t.body.removeChild(d[e].el), d.splice(e, 1)) : (d[e].y-- , d[e].scale += .004, d[e].alpha -= .013, d[e].el.style.cssText = "left:" + d[e].x + "px;top:" + d[e].y + "px;opacity:" + d[e].alpha + ";transform:scale(" + d[e].scale + "," + d[e].scale + ") rotate(45deg);background:" + d[e].color + ";z-index:99999"); requestAnimationFrame(r) } function o () { var t = "function" == typeof e.onclick && e.onclick; e.onclick = function (e) { t && t(), i(e) } } function i (e) { var a = t.createElement("div"); a.className = "heart", d.push({ el: a, x: e.clientX - 5, y: e.clientY - 5, scale: 1, alpha: 1, color: s() }), t.body.appendChild(a) } function c (e) { var a = t.createElement("style"); a.type = "text/css"; try { a.appendChild(t.createTextNode(e)) } catch (t) { a.styleSheet.cssText = e } t.getElementsByTagName("head")[0].appendChild(a) } function s () { return "rgb(" + ~~(255 * Math.random()) + "," + ~~(255 * Math.random()) + "," + ~~(255 * Math.random()) + ")" } var d = []; e.requestAnimationFrame = function () { return e.requestAnimationFrame || e.webkitRequestAnimationFrame || e.mozRequestAnimationFrame || e.oRequestAnimationFrame || e.msRequestAnimationFrame || function (e) { setTimeout(e, 1e3 / 60) } }(), n() }(window, document);
```

2. 在\themes\next\layout_layout.swig 文件末尾添加：

```
<!-- 页面点击小红心 -->
<script type="text/javascript" src="/js/src/clicklove.js"></script>
```
