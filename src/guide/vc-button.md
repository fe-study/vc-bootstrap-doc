---
title: vc-button
type: components
order: 1
---

* [online demo](https://iwaimai-bi-fe.github.io/vc-button/examples/)
* [github](https://github.com/iwaimai-bi-fe/vc-button)
* [npm](https://www.npmjs.com/package/vc-button)
* [download](https://github.com/iwaimai-bi-fe/vc-button/archive/master.zip)

## Install

``` npm
npm install vc-button --save
```

``` js
// build version
import vcButton from 'vc-button'

// recommend for *.vue project for small bundle size
import vcButton from 'vc-button/src/Button.vue'
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

### type 

type of button

* default: `确定`
* enum: `default | success | info | primary | warning | danger`
* type: `String`

### htmlType 

valid [html type](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button#attr-type) attribute

* default: `button`
* type: `String`

### label

button label

* type: `String`

### shape

shape of button icon

* default: `circle`
* enum: `circle | other`
* type: `String`

### disabled 

button disabled

* default: `false`
* type: `Boolean` 

### readonly 

button readonly

* default: `false`
* type: `Boolean` 

### size

size of button

* default `middle`
* enum: `large | middle | small | mini`
* type: `String`

### loading

is loading state?

* default: `false`
* type: `Boolean`

### loadingText

loadingText

* default: `加载中...`
* type: `String`

### style

* type: `Object`

## example

``` js
import Vue from 'vue'
import vcButton from 'vc-button/src'

new Vue({
    el: '#app',
    data () {
        return {
            label: 'use label, no slot',
            type: "warning",
            htmlType: 'button',
            loading: false,
            loadingText: 'loading中',
            size: 'middle',
            icon: 'remove',
            shape: '',
            disabled: false,
            style: {}
        }
    },
    components: {
        vcbutton
    }
})
```

``` html
<vc-button
    :type="type"
    :loading="loading"
    :loading-text="loadingText"
    :size="size"
    :disabled="disabled"
    :icon="icon"
    :shape="shape"
    :style='{ "border-radius": "0px" }'
    @click="handleClick('btn1', '@click', 'is slot, costom style')"
>
    slot & costom style
</vc-button>
```
