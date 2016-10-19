---
title: vc-tooltip
type: components 
order: 24
---

* [online demo](https://iwaimai-bi-fe.github.io/vc-tooltip/examples/)
* [github](https://github.com/iwaimai-bi-fe/vc-tooltip)
* [npm](https://www.npmjs.com/package/vc-tooltip)
* [download](https://github.com/iwaimai-bi-fe/vc-tooltip/archive/master.zip)

## Install

``` npm
npm install vc-tooltip --save
```

``` js
// build version
import vcTooltip from 'vc-tooltip'

// recommend for *.vue project for small bundle size
import vcTooltip from 'vc-tooltip/src/Tooltip.vue'
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

### trigger

* type: `String`
* default: `'hover'`

### effect

* type: `String`
* default: `'vc-scale'`

### content

* type: `String`

### placement

* type: `String`
* default: `'right'`

### show

* type: `Boolean`
* default: `false`

### closeable

* type: `Boolean`
* default: `true`

### functionalShow

* type: `Boolean`
* default: `false`

## example

* js

```js
import Vue from 'vue'
import vcTooltip from '../src'

new Vue({
    el: '#app',
    data () {
        return {
        }
    },
    methods: {
    },
    components: {
        vcTooltip
    }
})
```

```html
<vc-tooltip
    content="content tooltip from top"
    placement="top"
>
    <button class="btn btn-xs btn-info">hover我</button>
</vc-tooltip>
```
