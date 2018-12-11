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

