---
title: react Ref的使用
date: 2018-12-11 17:39:26
tags:
---
# refs
在react中，我们获取dom节点可以使用refs
1. 在我们要访问的虚拟DOM节点上加上ref属性
   `render(){return(<div ref={this.dom}></div>)}`
2. 在constructor中创建refs
   ```js
    constructor(props) {
        super(props)
        this.dom=React.createRef()
    }
   ```
3. 在componentDidMount中访问节点
   ```js
    componentDidMount(){
        console.log(this.dom.current)//打印出dom节点
    }
   ```