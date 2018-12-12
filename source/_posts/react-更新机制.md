---
title: react 更新机制
date: 2018-12-12 11:34:00
tags:
---
今天用react写代码，进行组件之间交互，遇到一个bug.
我想完成的结果是，点击A组件时，B组件颜色变化（原先蓝色就变绿色，原先绿色就变蓝色）。
但是最终做出结果出现一个bug,第一次颜色变化时，需要点击A组件两次。（按理说应该只需要一次）
排查发现是在B组件更新时用错传的参数。
在`componentWillUpdate(nextProps, nextState, nextContext){}`中
`nextProps`是最新的数据，而我用成了`this.props`.
所以我实际上一直取的是上一次数据来渲染这一次页面，出现了以上的bug.