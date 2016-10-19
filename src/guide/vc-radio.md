---
title: vc-radio
type: components 
order: 5
---

* [online demo](https://iwaimai-bi-fe.github.io/vc-radio/examples/)
* [github](https://github.com/iwaimai-bi-fe/vc-radio)
* [npm](https://www.npmjs.com/package/vc-radio)
* [download](https://github.com/iwaimai-bi-fe/vc-radio/archive/master.zip)

## Install

``` npm
npm install vc-radio --save
```

``` js
// build version
import vcRadio from 'vc-radio'

// recommend for *.vue project for small bundle size
import vcRadio from 'vc-radio/src/Radio.vue'
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

* type: `String`,
* default: `null`

### label

* type: `String`

### type

* type: `String`,
* default: `null`

### value

* default: `true`

### checked

* twoWay: `true`

### button

* type: `Boolean`,
* default: `false`

### disabled

* type: `Boolean`,
* default: `false`

### readonly

* type: `Boolean`,
* default: `false`

## example

* js

```js
import Vue from 'vue'
import vcRadio from '../src'

new Vue({
    el: '#app',
    data () {
        return {
            bools: {
                'true': true,
                'false': false
            },
            label: '选择2',
            value: true,
            button: true,
            type: 'success',
            checked: true,
            disabled: false,
            readonly: false
        }
    },
    components: {
        vcRadio
    }
})
```

```html
<vc-radio
    :label="label"
    :checked.sync="checked"
    :value="value"
    :button="button"
    :type="type"
    :disabled="disabled"
    :readonly="readonly"
>
    选择1
</vc-radio>(slot)
```
