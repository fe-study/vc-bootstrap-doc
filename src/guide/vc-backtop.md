---
title: vc-backtop
type: components
order: 32
---

* [online demo](https://iwaimai-bi-fe.github.io/vc-backtop/examples/)
* [github](https://github.com/iwaimai-bi-fe/vc-backtop)
* [npm](https://www.npmjs.com/package/vc-backtop)
* [download](https://github.com/iwaimai-bi-fe/vc-backtop/archive/master.zip)

## Install

``` npm
npm install vc-backtop --save
```

``` js
// build version
import vcBacktop from 'vc-backtop'

// recommend for *.vue project for small bundle size
import vcBacktop from 'vc-backtop/src/Backtop.vue'
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

### style

* type: `Object`,
* default: `
        width: DEFAULT_SIZE + 'px',
        height: DEFAULT_SIZE + 'px',
        top: 'auto',
        left: 'auto',
        right: '30px',
        bottom: '40px'

### interval

执行滚动位置检测的间隔

* type: `Number`,
* default: `32`

### scrollbarOffset

* type: `Number`,
* default: `100`

### acceleration: {

* type: `Number`,
* default: `.5`

### time

* type: `Number`,
* default: `10`

### mode

动画模式

* type: `String`,
* default: `'raf'`

## example

* js

```js
import Vue from 'vue'
import vcBacktop from '../src'

new Vue({
    el: '#app',
    data () {
        return {
            acceleration: .7,
            scrollbarOffset: "100",
            interval: 128,
            style: { "width": "60px","height": "60px","left":"auto", "top":"auto", "bottom": "60px", "right": "40px" },
            styleText: '{ "width": "60px","height": "60px","left":"auto", "top":"auto", "bottom": "60px", "right": "40px" }'
        }
    },
    components: {
        vcBacktop
    }
```

```html
<vc-backtop
    :scrollbar-offset="scrollbarOffset"
    :style.sync="style"
    :interval="interval"
    :acceleration="acceleration"
    :mode="mode"
>
</vc-backtop>
```
