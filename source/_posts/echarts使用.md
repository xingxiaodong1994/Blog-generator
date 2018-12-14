---
title: echarts使用
date: 2018-12-11 17:29:46
tags:
---
# 1. 安装echarts
    `npm install echarts --save`
# 2. 在模块中引入
    `import echarts from 'echarts'`
# 3. 简单使用
    ```js
     let myChart = echarts.init("DOM节点");
            myChart.setOption({
                title: {
                    text: 'ECharts 示例'
                },
                legend: {
                    data:['销量']
                },
                tooltip: {},
                xAxis: {
                    data: ['衬衫', '羊毛衫', '雪纺衫', '裤子', '高跟鞋', '袜子']
                },
                yAxis: {},
                series: [{
                    name: '销量',
                    type: 'bar',
                    data: [5, 20, 36, 10, 10, 20]
                }]
            });
    ```
# 4. 进阶使用
    ```js
    //第一步：引入
    import echarts from 'echarts'
    //第二步：初始化
    let myChart = echarts.init(document.getElementById("节点元素的id"));
    let option={
        //...配置信息
    }
    myChart.setOption(option)
    ```
# 5. 配置信息详解：
    ```js
    let option={
        backgroundColor: "red", //设置图表背景色
        grid: { //设置表格整体位置相对于给定区域的大小
                  top: '15%',
                  left: '8%',
                  right: '8%',
                  bottom: '8%',
                  containLabel: true,
              },
    }
    ```

