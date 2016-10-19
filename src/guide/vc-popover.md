---
title: vc-popover
type: components 
order: 23
---

* [online demo](https://iwaimai-bi-fe.github.io/vc-popover/examples/)
* [github](https://github.com/iwaimai-bi-fe/vc-popover)
* [npm](https://www.npmjs.com/package/vc-popover)
* [download](https://github.com/iwaimai-bi-fe/vc-popover/archive/master.zip)

## Install


``` npm
npm install vc-popover --save
```

``` js
// build version
import vcPopover from 'vc-popover'

// recommend for *.vue project for small bundle size
import vcPopover from 'vc-popover/src/Popover.vue'
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

### show

* type: `Boolean`,
* default: `false`

### functionalShow

函数式显示，此属性配合show来使用，只响应 `show` prop和控制，不受事件控制

* type: `Boolean`,
* default: `false`

### trigger

one of click, hover, focus, contextmenu

* type: `String`,
* default: `'click'`

### closeable

* type: `Boolean`,
* default: `true`

### effect

* type: `String`,
* default: `'vc-fade'`

### title

* type: `String`

### content

* type: `String`

### header

* type: `Boolean`,
* default: `true`

### placement

* type: `String`

## example

* js

```js
import Vue from 'vue'
import vcPopover from '../src'

new Vue({
    el: '#app',
    data () {
        return {
            bools: {
                'true': true,
                'false': false
            },
            show: true,
            closeable: false 
        }
    },
    methods: {
    },
    components: {
        vcPopover
    }
})
```

```html
<vc-popover 
    placement="left"
    title="Title"
    content="content"
>
    <button class="btn btn-xs btn-success">left</button>
</vc-popover>
```
