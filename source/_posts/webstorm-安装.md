---
title: webstorm 安装
date: 2018-12-11 09:20:36
tags:
---
# webstorm 安装
今天新入职，安装webstorm。
1. 首先进入官网下载按安装包，然后进行配置。
2. 对webStorm 进行汉化。把压缩包里的"resources_zh_CN.jar"拷贝到WebStorm安装目录下的lib目录，重启即可！
3. 压缩包下载地址(https://github.com/ewen0930/WebStorm-Chinese/releases)
# node更新
首先查看其版本

`node -v`

`npm -v`

然后更新至最新版本

更新npm ：

`npm install -g npm`
更新node版本是：



先清除npm缓存：`npm cache clean -f`

   

然后安装n模块：`npm install -g n ` 




升级node.js到最新稳定版：`n stable`


n后面也可以跟随版本号比如：`n v 3.7.3`


但是我运行上述命令没有成功，可能因为我是windows系统，我采用了最笨的办法，官网重新下载覆盖安装！！！

另外分享几个npm的常用命令

`npm -v `         #显示版本，检查npm 是否正确安装。
 
`npm install express`   #安装express模块
 
`npm install -g express`  #全局安装express模块
 
`npm list`         #列出已安装模块
 
`npm show express`     #显示模块详情
 
`npm update `       #升级当前目录下的项目的所有模块
 
`npm update express`    #升级当前目录下的项目的指定模块
 
`npm update -g express`  #升级全局安装的express模块
 
`npm uninstall express`  #删除指定的模块









