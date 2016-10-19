---
title: vc-autocomplete
type: guide
order: 3
---

* [online demo](https://iwaimai-bi-fe.github.io/vc-autocomplete/examples/)
* [github](https://github.com/iwaimai-bi-fe/vc-autocomplete)
* [npm](https://www.npmjs.com/package/vc-autocomplete)
* [download](https://github.com/iwaimai-bi-fe/vc-autocomplete/archive/master.zip)

## Install

``` npm
npm install vc-autocomplete --save
```

``` js
// build version
import vcAutocomplete from 'vc-autocomplete'

// recommend for *.vue project for small bundle size
import vcAutocomplete from 'vc-autocomplete/src/Autocomplete.vue'
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

比较模式

* type: String,

### autofocus

是否聚焦

* type: `Boolean`,
* default: `false`

### label

* type: `String`
* default: `''`

### placeholder

* type: `String`,

### parentModelKey

v-model like, 用于同步父组件model, 传进字符串作为key

* type: `String`, 

### mode

比较模式
    
* type: `String`,

* default: `remote`

### store

本地补全待比较池

* type: `Array`

### comparer: Function,

- @param {String} target1 比较目标1,即输入值
- @param {String} target2 比较目标2,即比较池中的item
- @return {Number} result 比较结果,返回相似度,越小说明越接近

### url

ajax请求地址

* type: `String`,

* required: `true`

### param

请求补充参数  e.g. 'city=131&word='

* type:`String`,

* default: `'word'`

dataParser

可传入解析器,不传则用内置的getDeepData

* type: `Function`,

### target

数据层级获取目标,由于每个api设计的返回结果的数据结构不一定一样,所以要求强制设置!default仅仅是个示例

* type: `String`,
* required: `true`,
* default: `'data.list'`

### limitKey

请求limit的key名，有默认值，可配置

* type: `String`,
* default: `'limit'`

### limit

add 'limit' query to AJAX URL which will be fetched

* type: `String`,
* default: `''`

### anchor

数据的锚点，即ajax返回的的每一个item中你需要取出来展示的特定key
    
* type: `String`,
* required: `true`

### anchorPlus

补充锚点，此处不是太好，局限了组件只能扩展一个显示锚点

* type: `String`,
* default: `'district'`

## example

* js

```js
import Vue from 'vue'
import vcAutocomplete from '../src'

new Vue({
    el: '#app',
    data () {
        return {
            vm: null,
            id: "",
            autofocus: false,
            label: "label",
            name: "name",
            placeholder: "尝试输入vue, api慢，请耐心等待",
            url: "https://api.github.com/search/issues",
            page: '1',
            per_page: '10',
            target: "items",
            anchor: "body",
            parentModelKey: "vm",
            mode: 'remote',
            store: [],
            storeStr: '今天是星期五,今天是周五,明天咱们去钓鱼吧,明天咱们去玩游戏,明天咱们吃火锅,下周今天是星期几,明天天气怎么样, 啦啦啦啦啦啦啦'
        }
    },
    computed: {
        store () {
            return this.storeStr.split(',')
        },
        queryBase () {
            return `page=${this.page}&per_page=${this.per_page}&q`
        }
    },
    components: {
        vcAutocomplete
    }
}
```

```html
<vc-autocomplete
    :label="mode"
    :mode="mode"
    :id="id"
    :name="name"
    :autofocus="autofocus"
    :placeholder="placeholder"
    :url="url"
    :param="queryBase"
    :target="target"
    :anchor="anchor"
    :data-parser="parser"
    :parent-model-key="parentModelKey"
>
</vc-autocomplete>
```
