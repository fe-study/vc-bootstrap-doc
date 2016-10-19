---
title: vc-table
type: components 
order: 26
---

* [online demo](https://iwaimai-bi-fe.github.io/vc-table/examples/)
* [github](https://github.com/iwaimai-bi-fe/vc-table)
* [npm](https://www.npmjs.com/package/vc-table)
* [download](https://github.com/iwaimai-bi-fe/vc-table/archive/master.zip)

## Install

``` npm
npm install vc-table --save
```

``` js
// build version
import vcTable from 'vc-table'

// recommend for *.vue project for small bundle size
import vcTable from 'vc-table/src/Table.vue'
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

### name

* type: `String`
* default: `'vc-table' + Date.now()`

### tpl

* type: `String` // 放出tpl属性，让用户定制组件template，支持一个字符串来代表字符串模板或模板dom标示

### data

* type: `Array`

### dataParser

a callback to parse each `entry[key]` in template

* type: `Function`

### dataPlus

* type: `Object` // 高级定制: 外部可提供一个数据对象供模板使用(比如传入baseUrl)

### columns

* type: `Array`

### columnsMap

* type: `Object` // key => value对照映射，用于可能的中文filter

### title

表头

* type: `String`

### titleAlign

* type: `String`
* default: `'center'`

### tableFixed

table-layout: fixed的使用

* type: `Boolean`
* default: `false`

### searchable

是否可搜索过滤

* type: `Boolean`
* default: `false`

### filterKey

* type: `String`

### filterLabel

* type: `String`
* default: `'筛选'`

### sortable

* type: `Boolean`
* default: `false`

### showTableHeader

* type: `Boolean`
* default: `true`

### exportLabel

* type: `String`
* default: `'导出'`

### exportable

是否显示导出按钮(会dispatch排序参数等相关信息)

* type: `Boolean`
* default: `false`

## example

* js

```js
import Vue from 'vue'
import vcTable from '../dist/build.js'

new Vue({
    el: '#app',
    data () {
        return {
            bools: {
                'true': true,
                'false': false
            },

            name: "name",
            dataPlus: {},

            columns: ['c0', 'c1', 'c2', 'c3', 'c4', 'c5', 'c7', 'c8'],
            columnsMap: {
                'c0': '中文0',
                'c1': '中文1',
                'c2': '中文2',
                'c3': '中文3',
                'c4': '中文4',
                'c5': '中文5',
                'c6': '中文6',
                'c7': '中文7',
                'c8': '中文8',
                'c9': '中文9'
            },
            data: {},
            title: "表格的标题",
            titleAlign: "center",
            showTableHeader: true, 
            exportLabel:"导出",
            exportable: true,
            searchable: true,
            filterKey: 'vim',
            filterLabel: '过滤',
            sortable: true,
            tableFixed: false
        }
    },
    created () {
        this.data = [{
            'c0': 0,
            'c1': 1,
            'c2': '2',
            'c3': 3,
            'c4': '2.234243423423424',
            'c5': 2,
            'c6': 4,
            'c7': 7,
            'c8': 'vim',
            'c9': 9
        }, {
            'c0': 1,
            'c1': 1,
            'c2': '7',
            'c3': 3,
            'c4': '2.32442423423423424342',
            'c5': 5,
            'c6': 2,
            'c7': 7,
            'c8': 'vue',
            'c9': 9
        }, {
            'c0': 2,
            'c1': 2,
            'c2': '1',
            'c3': 3,
            'c4': 2.23423423424,
            'c5': 7,
            'c6': 6,
            'c7': 8,
            'c8': 'components',
            'c9': 9
        }, {
            'c0': 3,
            'c1': 1,
            'c2': '1',
            'c3': 3,
            'c4': 4,
            'c5': 2,
            'c6': 7,
            'c7': 7,
            'c8': 'vc-table',
            'c9': 9
        }, {
            'c0': 4,
            'c1': 1,
            'c2': '2',
            'c3': 3,
            'c4': 4.234234234234,
            'c5': 2,
            'c6': 1,
            'c7': 7,
            'c8': 'mvvm',
            'c9': 9
        }, {
            'c0': 5,
            'c1': 2,
            'c2': '6',
            'c3': 3,
            'c4': 1.3245342423423424234234,
            'c5': 5,
            'c6': 6,
            'c7': 7,
            'c8': 'bootstrap',
            'c9': 9
        }, {
            'c0': 6,
            'c1': 1,
            'c2': '6',
            'c3': 3,
            'c4': 4.23444444444444,
            'c5': 7,
            'c6': 1,
            'c7': 7,
            'c8': 'hhkb',
            'c9': 9
        }]
    },
    components: {
        vcTable
    },
    events: {
        TABLE (msg) {
            // do your own handler with action & data in msg 
            let action = msg.action
            let data = msg.data
            console.log(action, data, msg)
        }
    }
})
```

```html
<vc-table
    :name="name"
    :columns="columns"
    :columns-map="columnsMap"
    :data="data"
    :data-plus="dataPlus"
    :title="title"
    :title-align="titleAlign"
    :show-table-header="showTableHeader"
    :export-label="exportLabel"
    :exportable="exportable"
    :searchable="searchable"
    :filter-key="filterKey"
    :filter-label="filterLabel"
    :sortable="sortable"
    :table-fixed="tableFixed"
>
</vc-table>
```
