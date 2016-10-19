---
title: vc-tag
type: components
order: 27
---

* [online demo](https://iwaimai-bi-fe.github.io/vc-tag/examples/)
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

### show

* type: `Boolean`
* default: `true`

### label

* type: `String`

### size

* type: `String`
* default: `'default'`

### closeable

* type: `Boolean`

### disabled

* type: `Boolean`
* default: `false`

### status

* type: `String`

### onClose

* type: `Function`

### afterClose

animationend callback

* type: `Function`


## example

* js

```js
import Vue from 'vue'
import vcTag from '../dist/build.js'

new Vue({
    el: '#app',
    data () {
        return {
            bools: {
                'true': true,
                'false': false
            },
            show: true,
            label: '我是标签1',
            size: 'default',
            status: 'success',
            disabled: false,
            closeable: true,
            onClose () {
                console.log('will close tag')
            },
            afterClose () {
                console.log('after close tag')
            }
        }
    },
    components: {
        vcTag
    }
})
```

```html
<vc-tag
    :show.sync="show"
    :label="label"
    :disabled="disabled"
    :size="size"
    :status="status"
    :closeable="closeable"
    :on-close="onClose"
    :after-close="afterClose"
>
</vc-tag>
```
