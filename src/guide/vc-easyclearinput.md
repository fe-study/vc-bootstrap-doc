---
title: vc-easyclearinput
type: components 
order: 10
---

* [online demo](https://iwaimai-bi-fe.github.io/vc-easyclearinput/examples/)
* [github](https://github.com/iwaimai-bi-fe/vc-easyclearinput)
* [npm](https://www.npmjs.com/package/vc-easyclearinput)
* [download](https://github.com/iwaimai-bi-fe/vc-easyclearinput/archive/master.zip)

## Install

``` npm
npm install vc-easyclearinput --save
```

``` js
// build version
import vcEasyclearinput from 'vc-easyclearinput'

// recommend for *.vue project for small bundle size
import vcEasyclearinput from 'vc-easyclearinput/src/Easyclearinput.vue'
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

* type: `String`,
* default: `'text'`

### value

* twoWay: `true`,

### label
* type: `String`

### placeholder

* type: `String`

### infoText
    
* type: `String`,
* default: `''`

### disabled

* type: `Boolean`,
* default: `false`

### readonly

* type: `Boolean`,
* default: `false`


### autofocus

* type: `Boolean`,
* default: `false`

### width

* type: `Number | String`,
* default: '250' 

### icon

* type: `Boolean`,
* default: `false`

### status

* type: `String`,
* default: `''`

### onFocus

### focus回调

* type: `Function`,
* default: `function () {}`

### onBlur

### blur回调

* type: `Function`,
* default: `function () {}`

### onClear

### onClear回调

* type: `Function`,
* default: `function () {}`

## example

* js

```js
import Vue from 'vue'
import vcEasyclearinput from '../src'

new Vue({
    el: '#app',
    data () {
        return {
            bools: {
                'true': true,
                'false': false
            },
            noSlot: true,
            label: 'label',
            type: "text",
            autofocus: true,
            disabled: false,
            readonly: false,
            value: 'content',
            placeholder: 'placeholder',
            infoText: '请输入正确的用户名',
            status: '',
            width: '400',
            icon: false,
            onInput: function () {
                console.log('onInput')
            },
            onChange: function (e) {
                console.log('onChange', e)
            },
            onClear: function () {
                console.log('onClear')
            },
            onFocus: function (e) {
                console.log('onFocus', e)
            },
            onBlur: function (e) {
                console.log('onBlur', e)
            }
        }
    },
    components: {
        vcEasyclearinput
    }
})
```

```html
<vc-easyclearinput
    :type="type"
    :label="label"
    :placeholder="placeholder"
    :value.sync="value"
    :info-text="infoText"
    :autofocus="autofocus"
    :disabled="disabled"
    :readonly="readonly"
    :width="width"
    :icon="icon"
    :status="status"
    :on-clear="onClear"
    :on-focus="onFocus"
    :on-blur="onBlur"
    @input="onInput"
    @change="onChange"
    oninput="console.log('native oninput, DOM0 inline event style')"
>
    <span slot="input-before" class="input-group-addon">@</span>
</vc-easyclearinput>
```
