---
title: vc-icon
type: components 
order: 2
---

* [online demo](https://iwaimai-bi-fe.github.io/vc-icon/examples/)
* [github](https://github.com/iwaimai-bi-fe/vc-icon)
* [npm](https://www.npmjs.com/package/vc-icon)
* [download](https://github.com/iwaimai-bi-fe/vc-icon/archive/master.zip)

## Install

```npm
npm install vc-icon --save
```

``` js
// build version
import vcIcon from 'vc-icon'

// recommand for *.vue project for small bundle size
import vcIcon from 'vc-icon/src/Icon.vue'
```

``` js 
// commonjs
require('dist/build.min.js')
```

```html
// script tag
<script src='./dist/build.min.js'></script>
```

## Usage

## props

### type 

name of icon, full Bootstrap [Glyphicons Halflings](http://glyphicons.com/) icons support

* type: `String`

### shape 

shape of icon

* default: `circle`
* enum: `circle | other`
* type: `String`

### size 

icon size

* default: `small`
* enum: `large | middle | small | mini | Number`
* type: `String|Number` 

## example

``` js
import Vue from 'vue'
import vcIcon from 'vc-icon/src'

new Vue({
    el: '#app',
    data () {
        return {
            type: 'ok',
            shape: 'circle',
            size: 'large'
        }
    },
    components: {
        vcIcon
    }
})
```

``` html 
<vc-icon 
    :type="type"
    :shape="shape"
    :size="large"
>
</vc-icon>
```
