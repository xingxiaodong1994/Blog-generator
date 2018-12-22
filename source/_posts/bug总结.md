---
title: bug总结
date: 2018-12-20 14:38:14
tags:
---
1. bug1:合并代码后Echarts图表不见了！
   发现原因：在template中含有echarts的组件写了两次，出现冲突。
   解决办法： 删除掉重复的组件。
2. bug2:函数f1(index,name)传参时报错：name未定义。
   发现原因：index传的参数为数字类型，未报错。name为字符串类型，报错。具体原因不清楚。
   解决办法：name参数也传数字，然后在函数体内部再通过判断把数字变成相应字符串。
3. bug3: vue渲染数据不成功。
   发现原因：在组件中数据经过data转换地址后不再渲染！！！
   ```js
    //vue的模板
    <template>
     <div class="introduction">
        <div class="introduction-title">
              {{data.introduction}} //不渲染！！！
          </div>
          <div class="introduction-content">
              {{BasicInfoData.introduction}}//渲染
          </div>
        </div>
    </template> 

    <script>
      props: ["BasicInfoData"],
      data() {
        return {
          data: this.BasicInfoData
        };
      }
    </script>
   ```
   解决办法：直接使用porp中的地址，不要转换地址。
4. 问题：vue组件重新渲染以后，组件内部Echarts图表未渲染。
   原因：echarts图表未监听到数据变化。
   解决办法：使用watch监听函数监听数据变化，然后重新调用echarts.
   ```js
    watch:{
      data(value,oldValue){
        echarts(value)
      }
    }
   ```