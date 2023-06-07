# 信息系统设计_智能存储平台
## 项目介绍
本项目基于[gohttpserver](https://github.com/codeskyblue/gohttpserver)进行修改，实现了一个简单的文件管理系统，支持文件上传、下载、删除、重命名、移动、复制、分享、搜索等功能（具体使用方法参考[gohttpserver](gohttpserver.md)文档介绍）。前端页面修改了标题和banner栏功能，使用监控功能替换了banner的二维码页面（监控功能基于`python`修改实现）并修改了对话框样式和监控图像匹配。
## 自定义功能
静态资源位于[assets](./assets/)目录下，其中[index.html](./assets/index.html)为静态页面入口，几个由"[[ ]]"括号对包裹的变量会在gohttpserver的返回结果中被替换成[main.go](./main.go)中定义的变量值，同时删除注释。文件服务器提供功能开关（例如`auth, upload, delete`）可以通过`gohttpserver`的命令行参数进行修改，具体参考[gohttpserver](gohttpserver.md)文档介绍。
## Tips
### 项目部署
本地测试编译参考[gohttpserver](gohttpserver.md)文档：
```bash
$ go build [-o gohttpserver]
```
golang一键arm交叉编译：
```bash
$ CGO_ENABLED=0 GOOS=linux GOARCH=arm go build
```
编译所需环境变量说明见[跨平台交叉编译 · Go语言中文文档](https://www.topgoer.com/%E5%85%B6%E4%BB%96/%E8%B7%A8%E5%B9%B3%E5%8F%B0%E4%BA%A4%E5%8F%89%E7%BC%96%E8%AF%91.html)
### 前端修改
项目依赖于常见前端框架[bootstrap](https://getbootstrap.com/)和[jquery](https://jquery.com/), [vue.js](https://cn.vuejs.org/), [font-awesome(4.6.3)](https://fontawesome.com/v4/)，前端页面修改请参考相应框架官方文档。

目前的前端页面仿照原项目的页面元素写了一个监控对话框，修改了对话框宽度，更改了回顶部top键的图标和显示风格。