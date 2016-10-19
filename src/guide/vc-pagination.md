---
title: vc-pagination
type: components 
order: 29
---

* [online demo](https://iwaimai-bi-fe.github.io/vc-pagination/examples/)
* [github](https://github.com/iwaimai-bi-fe/vc-pagination)
* [npm](https://www.npmjs.com/package/vc-pagination)
* [download](https://github.com/iwaimai-bi-fe/vc-pagination/archive/master.zip)

## Install

``` npm
npm install vc-pagination --save
```

``` js
// build version
import vcPagination from 'vc-pagination'

// recommend for *.vue project for small bundle size
import vcPagination from 'vc-pagination/src/Pagination.vue'
```

``` js 
// commonjs
require('./dist/build.min.js')
```

``` html
// script tag
<script src='./dist/build.min.js'></script>
```

## Usage

## props

### simple

普通版本
    
* type: `Boolean`,
* default: `false`

### align
    
* type: `String`,
* default: `'center'`

### prevText

* type: `String`,
* default: `'‹'`

### nextText

* type: `String`,
* default: `'›'`

### firstPageText

* type: `String`,
* default: `'首页'`

### lastPageText

* type: `String`,
* default: `'末页'`

### displayNum

可看见的页码数目

* type: `Number`,
* default: 6

### edgeNum

页码较多时，前后空余的可选页码数量

* type: `Number`,
* default: `2`

### current

当前页码数

    
* twoWay: `true`,
* type: `Number`,
* default: `1`

### pageSize

页面数据量

    
* twoWay: `true`,
* type: `Number`,
* default: `10`

### total

全部结果集数目

* type: `Number`,
* default: `0`

### onPageChange

* type: `Function`,
* default: `function () {}`

### jumpable

是否显示跳转控件（页码输入框和跳转按钮）

* type: `Boolean`,
* default: `true`

### goLabel

跳转按钮的文案

* type: `String`,
* default: `'跳转'`

### invalidCallback: {

* type: `Function`,
* default: `function () {}`

### pageSizeEditable

* type: `Boolean`,
* default: `true` 

### pageSizeArr

* type: `Array`,
* default: `[10, 20, 40, 100]`

### onPageSizeChange

* type: `Function`,
* default: `function () {}`

## example

* js

```js
import Vue from 'vue'
import vcPagination from '../dist/build.js'

new Vue({
    el: '#app',
    data () {
        return {
            bools: {
                'true': true,
                'false': false
            },
            simple: true,
            align: 'center',
            firstPageText: '首页',
            lastPageText: '末页',
            displayNum: 6,
            edgeNum: 2,
            total: 200,
            current: 1,
            pageSize: 20,
            pageSizeEditable: true, 
            pageSizeArr: [10, 20, 40, 100],
            jumpable: true,
            goLabel: '跳转',
            invilidPageHandler: null,
            onPageChange: null,
            onPageSizeChange: null,

            pageSizeArrStr: '', // just for demo
        }
    },
    methods: {
        setPageSizeArr: function () {
            this.pageSizeArr = this.pageSizeArrStr.replace(/\s/, '').split(',')
        }
    },
    components: {
        vcPagination
    }
})
```

```html
<vc-pagination
    :simple="simple"
    :align="align"
    :first-page-text="firstPageText"
    :last-page-text="lastPageText"
    :display-num="displayNum"
    :edge-num="edgeNum"
    :total="total"
    :current.sync="current"
    :page-size.sync="pageSize"
    :page-size-editable="pageSizeEditable"
    :page-size-arr="pageSizeArr"
    :jumpable="jumpable"
    :go-label="goLabel"
    :invilid-page-handler="invilidPageHandler"
    :on-page-change="onPageChange"
    :on-page-size-change="onPageSizeChange"
>
</vc-pagination>
```
