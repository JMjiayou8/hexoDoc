---
title: vue常见细节问题总结
date: 2019-9-03 09:16:37
tags:
  - vue
---

整理一波 vue 开发过程中遇到的比较细节但很无奈的小问题吧

#### 刷新显示差值语句

#### element-ui 下拉框选中不赋值

#### 数组赋值操作

#### vue 获取 dom 元素位置

```javascript
this.$refs['xx'].getBoundingClientRect()
// 获取组件高度
this.$refs.xx.$el.offsetHeight
// 设置元素样式
this.$refs.xx.style.top = 100 + 'px'
```
