---
title: Introduction
type: components
order: 0
---

vc-bootstrap,一个基于vue的组件库。

* 简洁而不简单
* 数据驱动
* 分布式组件管理
* 模块化


## 如何使用

通过 npm 包管理工具安装, vc-bootstrap 采用分布式的组件管理方式，每个组件单独以 npm 包的形式发布，可以分别安装使用，也可以整体安装，vc-bootstrap 其实只是将各个组件整合起来而已。

* 样式依赖

vc-bootstrap 依赖于 bootstrap 3.x, 在使用之前需要先引入bootstrap样式文件。

* [bootstrap(en)](http://getbootstrap.com/)
* [bootstrap(cn)](http://www.bootcss.com/)

bootstrap(CDN)

```html
<link href="//cdn.bootcss.com/bootstrap/3.3.6/css/bootstrap.css" rel="stylesheet">
```

### 模块加载

* 整体引入

```node
npm install vc-bootstrap --save
```

* 按组件引入

```node
//安装分页组件
npm install vc-pagination --save

//安装 modal 组件
npm install vc-modal --save
```

### script tag 导入

```html
//请先下载vcBootstrap.js 文件
<script src='/js/vc-bootstrap.js'></script>
```
