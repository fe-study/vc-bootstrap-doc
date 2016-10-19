---
title: vc-dropdown
type: components
order: 17
---

* [online demo](https://iwaimai-bi-fe.github.io/vc-dropdown/examples/)
* [github](https://github.com/iwaimai-bi-fe/vc-dropdown)
* [npm](https://www.npmjs.com/package/vc-dropdown)
* [download](https://github.com/iwaimai-bi-fe/vc-dropdown/archive/master.zip)

## Install

``` npm
npm install vc-dropdown --save
```

``` js
// build version
import vcDropdown from 'vc-dropdown'

// recommend for *.vue project for small bundle size
import vcDropdown from 'vc-dropdown/src/Dropdown.vue'
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

### label

* type: `String`,
* default: `'下拉菜单'`

### menus

* type: `Object`,
* default: `
    'menu0': '下拉菜单0',
    'menu1': '下拉菜单1',
    'menu2': '下拉菜单2'
    `

### open

* type: `Boolean`,
* default: `false` 

### onClick
* type: `Function`

## example

* js

```js
import Vue from 'vue'
import vcDropdown from '../dist/build.js'

new Vue({
    el: '#app',
    data () {
        return {
            bools: {
                'true': true,
                'false': false
            },
            useSlot: true,
            label: '下拉菜单',
            open: true,
            customClick (value) {
                alert('自定义点击回调, value = ' + value)
                console.log('自定义点击回调', value)
            },
            onClick (key, value, index) {
                alert('点击回调' + index)
                console.log('点击回调', key, value, index)
            }
        }
    },
    components: {
        vcDropdown
    }
})
```

```html
<vc-dropdown
    v-if="useSlot"
    :label="label"
    :open="open"
>
    <a class="dropdown-toggle dropdown-trigger" data-dropdown-trigger="vc-dropdown">
        <span>下拉菜单自定义</span>
        <span class="caret"></span>
    </a>
    <ul slot="dropdown-menu" class="dropdown-menu">
        <li @click="customClick(1)"><a>用户手机号</a></li>
        <li @click="customClick(2)"><a>用户ID</a></li>
    </ul>
</vc-dropdown>

<vc-dropdown
    v-if="!useSlot"
    :label="label"
    :open="open"
    :on-click="onClick"
></vc-dropdown>
```
