---
title: mxGraph
date: 2018-8-22 09:16:37
tags:
  - mxGraph
---

#### mxEventSource

创建子类

```javascript
function MyClass() {
  ...
}

MyClass.prototype = new mxEventSource()
MyClass.prototype.constructor = MyClass
```

已知子类：`mxGraphModel, mxGraph, mxGraphView, mxEditor, mxCellOverlay, mxToolbar, mxWindow`

#### mxEditor

1. `actions、addActions、addAction` action 的一个集合
2. 读/写 图形文件
3. 节点属性 保存在 `mxEditor.templates`
4. Popupmenu and Toolbar

#### mxGraph

1. 背景图片
2. 节点图片、节点 Label、In-place Editing
3. Tooltips 提示信息
4.
