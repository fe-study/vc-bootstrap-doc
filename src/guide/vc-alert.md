---
title: vc-alert
type: components
order: 13
---

* [online demo](https://iwaimai-bi-fe.github.io/vc-alert/examples/)
* [github](https://github.com/iwaimai-bi-fe/vc-alert)
* [npm](https://www.npmjs.com/package/vc-alert)
* [download](https://github.com/iwaimai-bi-fe/vc-alert/archive/master.zip)

## Install

``` npm
npm install vc-alert --save
```

``` js
// build version
import vcAlert from 'vc-alert'

// recommend for *.vue project for small bundle size
import vcAlert from 'vc-alert/src/Alert.vue'
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

type of alert

* type: `String`

### mode 

是否固定文档流

* default: `fixed`
* type: `String`

### dismissable

是否有关闭按钮

* default: `false`
* type: `Boolean` 

### show

是否显示

* type: `Function`
* twoWay: `true`

### duration

可选的持续时间

* type: `Number`

### width

宽度

* type: `String`

### placement

定位

* type: `String`

### positionClass

* type: `String`


## example

* js

```js
import Vue from 'vue'
import vcAlert from '../src'

new Vue({
    el: '#app',
    data () {
        return {
            bools: {
                'true': true,
                'false': false
            },
            show: false,
            mode: 'fixed',
            type: 'success',
            width: '500',
            placement: 'top',
            duration: '3000',
            dismissable: true,
            positionClass: null
        }
    },
    components: {
        vcAlert
    }
}
```

```html
<vc-alert 
    :show.sync="show"
    :mode="mode"
    :placement="placement"
    :duration="duration"
    :type="type"
    :width="width"
    :position-class="positionClass"
    :dismissable="dismissable"
>
    <span class="icon-ok-circled alert-icon-float-left"></span>
    <strong>Well Done!</strong>
    <p>You successfully read this important alert message.</p>
</vc-alert>
```
