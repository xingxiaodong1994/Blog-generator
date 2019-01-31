---
title: dva Loading 使用
date: 2019-01-30 16:04:23
tags:
---
我们写页面的时候常常要用到loading,来表示加载状态。
在dva中，dva 项目的 index.js 文件：
```js
import createLoading from 'dva-loading';

const app = dva();

app.use(createLoading());
```
`export default connect(({ app, loading }) => ({ app, loading }))(App);`
打印一下 loading 对象，可看到内容如下：
```js
loading: {
  global: false,
  models: {app: false},
  effects: {app: false}
}
```
loading 有三个方法，其中 loading.effects['user/query'] 为监听单一异步请求状态，当页面处于异步加载状态时该值为 true，当页面加载完成时，自动监听该值为 false。
如果同时发出若干个异步请求，需求是当所有异步请求都响应才做下一步操作，可以使用 loading.global() 方法，该方法监听所有异步请求的状态。

我们使用antd框架时：
可以引用：
`import React, {Spin} from 'react';`
```js
const {loading}=this.props
// const isShowPop=loading.effects["productAnalysisTableDataModels/fetchTableData"]
const isShowPop=loading.global
render(){
 <Spin spinning={isShowPop}>
        <div>组件</div>
    </Spin>
}
   
```


