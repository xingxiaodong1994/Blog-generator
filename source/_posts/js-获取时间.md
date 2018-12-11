---
title: js 获取时间
date: 2018-12-11 10:10:44
tags:
---
```js
    let currentTime=new Date()
    console.log(currentTime)
    //Tue Dec 11 2018 10:22:27 GMT+0800 (中国标准时间)
    // 得到一个当前GMT时间
    console.log(currentTime.getFullYear());//年
    console.log(currentTime.getMonth());//月
    console.log(currentTime.getDate());//日
    console.log(currentTime.getDay());//星期
    console.log(currentTime.toLocaleDateString());
    console.log(currentTime.getSeconds());
     let hours=currentTime.getHours();//时
     let minutes=currentTime.getMinutes();//分
     let seconds=currentTime.getSeconds();//秒
     let time=currentTime.toLocaleDateString()//2018/12/11这样格式的时间
```
