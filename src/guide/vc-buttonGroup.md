---
title: vc-buttonGroup
type: components
order: 6
---

* [online demo](https://iwaimai-bi-fe.github.io/vc-buttonGroup/examples/)
* [github](https://github.com/iwaimai-bi-fe/vc-buttonGroup)
* [npm](https://www.npmjs.com/package/vc-buttonGroup)
* [download](https://github.com/iwaimai-bi-fe/vc-buttonGroup/archive/master.zip)

## Install

``` npm
npm install vc-buttonGroup --save
```

``` js
// build version
import vcButtonGroup from 'vc-buttonGroup'

// recommend for *.vue project for small bundle size
import vcButtonGroup from 'vc-buttonGroup/src/ButtonGroup.vue'
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

### value

值

### buttons

* type: `Boolean`,
* default: `true`

### group

是否是 `group` 模式

* type: `Boolean`,
* default: `true`

### type

* type: `String`,
* default: `'default'`

## example

* js

```js
import Vue from 'vue'
import vcButtonGroup from '../src'
import vcCheckbox from '../../vc-checkbox/src'
import vcRadio from '../../vc-radio/src'

new Vue({
    el: '#app',
    data () {
        return {
            bools: {
                'true': true,
                'false': false
            },
            checkValue: null,
            radioValue: null,
            buttons: true
        }
    },
    components: {
        vcButtonGroup,
        vcCheckbox,
        vcRadio
    }
})
```

```html
<vc-button-group
    :value.sync="radioValue"
    :buttons="buttons"
>
    <vc-radio type="success" value="one">中文第一个</vc-radio>
    <vc-radio type="warning" value="two">two</vc-radio>
    <vc-radio type="danger" value="three">three</vc-radio>
    <vc-radio type="info" value="four">four</vc-radio>
</vc-button-group>

<pre>radio: {{ radioValue | json 4 }}</pre>

<hr>

<vc-button-group
    :value.sync="checkValue"
    :buttons="buttons"
>
    <vc-checkbox type="success" value="one">one</vc-checkbox>
    <vc-checkbox type="warning" value="two">中文二</vc-checkbox>
    <vc-checkbox type="danger" value="three">three</vc-checkbox>
    <vc-checkbox type="info" value="four">four</vc-checkbox>
</vc-button-group>

<pre>checkbox: {{ checkValue | json 4 }}</pre>
```
