---
title: vc-checkbox
type: components
order: 4
---

* [online demo](https://iwaimai-bi-fe.github.io/vc-checkbox/examples/)
* [github](https://github.com/iwaimai-bi-fe/vc-checkbox)
* [npm](https://www.npmjs.com/package/vc-checkbox)
* [download](https://github.com/iwaimai-bi-fe/vc-checkbox/archive/master.zip)

## Install

``` npm
npm install vc-checkbox --save
```

``` js
// build version
import vcCheckbox from 'vc-checkbox'

// recommend for *.vue project for small bundle size
import vcCheckbox from 'vc-checkbox/src/Checkbox.vue'
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

* type: `String | Number`

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

### type

* type: `String`,
* default: `null`

## example

* js

```js
import Vue from 'vue'
import vcCheckbox from '../src'

new Vue({
    el: '#app',
    data () {
        return {
            bools: {
                'true': true,
                'false': false
            },
            label: '选择2, not slot',
            value: true,
            button: true,
            type: 'success',
            checked: true,
            disabled: false,
            readonly: false
        }
    },
    components: {
        vcCheckbox
    }
})
```

```html
<vc-checkbox
    :label="label"
    :checked.sync="checked"
    :value="value"
    :button="button"
    :type="type"
    :disabled="disabled"
    :readonly="readonly"
>
    slot
</vc-checkbox>

<vc-checkbox
    :label="label"
    :checked.sync="checked"
    :value="value"
    :button="button"
    :type="type"
    :disabled="disabled"
    :readonly="readonly"
>
</vc-checkbox>
```
