---
title: vc-toast
type: components 
order: 18
---

* [online demo](https://iwaimai-bi-fe.github.io/vc-toast/examples/)
* [github](https://github.com/iwaimai-bi-fe/vc-toast)
* [npm](https://www.npmjs.com/package/vc-toast)
* [download](https://github.com/iwaimai-bi-fe/vc-toast/archive/master.zip)

## Install

``` npm
npm install vc-toast --save
```

``` js
// build version
import vcToast from 'vc-toast'

// recommend for *.vue project for small bundle size
import vcToast from 'vc-toast/src/Toast.vue'
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

### toasts

* type: `Array`
* default: `[]`

### stack

* type: `Boolean`
* default: `false`

### top

* type: `String`

### right

* type: `String`

### duration

全局设置duration，优先级大于子元素默认duraiton，小于快捷函数调用传入

* type: `Number | String` 

`Toast-Item prop`

### id

* type: `Number | String`

### message

* type: `String`

### type

* type: `String`
* default: `'info'`

### duration

* type: `Number | String`

### icon

* type: `String`

## example

* js

```js
import Vue from 'vue'
import vcToast from '../src'

new Vue({
    el: '#app',
    data () {
        return {
            bools: {
                true: true,
                false: false
            },
            message: 'toast message',
            duration: 2,
            type: 'info',
            icon: 'ok',
            toasts: [],
            top: null,
            right: null,
            stack: false,
            duration: 3,
            classname: 'toast-position'
        }
    },
    ready () {
        Toast.info('来自快捷函数调用的10秒 info Toast', 10)
    },
    methods: {
        showMeTenSeconds () {
            this.duration = 10
            this.push()
        },
        toggleMode () {
            this.stack = !this.stack
        },
        success () {
            this.type = 'success'
            this.duration = 2
            this.push()
        },
        danger () {
            this.type = 'danger'
            this.duration = 2
            this.push()
        },
        info () {
            this.type = 'info'
            this.duration = 2
            this.push()
        },
        warning () {
            this.type = 'warning'
            this.duration = 2
            this.push()
        },
        push () {
            let index = this.toasts.length
            this.toasts.push({
                duration: this.duration,
                message: `msg: ${index}: ${this.message}`,
                type: this.type
            })
        }
    },
    components: {
        vcToast
    }
})
```

```html
<vc-toast
    :toasts="toasts"
    :top="top"
    :right="right"
    :stack="stack"
    :duration="duration"
>
</vc-toast>
```
