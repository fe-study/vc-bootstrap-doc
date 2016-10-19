---
title: vc-panel
type: components
order: 34
---

* [online demo](https://iwaimai-bi-fe.github.io/vc-panel/examples/)
* [github](https://github.com/iwaimai-bi-fe/vc-tag)
* [npm](https://www.npmjs.com/package/vc-tag)
* [download](https://github.com/iwaimai-bi-fe/vc-tag/archive/master.zip)

## Install

``` npm
npm install vc-tag --save
```

``` js
// build version
import vcTag from 'vc-tag'

// recommend for *.vue project for small bundle size
import vcTag from 'vc-tag/src/Tag.vue'
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

### title

* type: `String`

### subTitle

* type: `String`

### info

* type: `String`

### type
    
* type: `String`
* default: `'info'`

## example

* js

```js
import Vue from 'vue'
import vcPanel from '../src'

new Vue({
    el: '#app',
    data () {
        return {
            title: '主标题在此',
            subTitle: '副标题再此',
            info: '额外信息写在这',
            type: 'info'
        }
    },
    methods: {
        success () {
            this.type = 'success'
        },
        danger () {
            this.type = 'danger'
        },
        warning () {
            this.type = 'warning'
        }
    },
    components: {
        vcPanel
    }
})
```

```html
<vc-panel
    :title="title"
    :sub-title="subTitle"
    :info="info"
    :type="type"
>
    <div>panel content body</div>
</vc-panel>
```
