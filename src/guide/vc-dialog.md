---
title: vc-dialog
type: components
order: 21
---

* [online demo](https://iwaimai-bi-fe.github.io/vc-dialog/examples/)
* [github](https://github.com/iwaimai-bi-fe/vc-dialog)
* [npm](https://www.npmjs.com/package/vc-dialog)
* [download](https://github.com/iwaimai-bi-fe/vc-dialog/archive/master.zip)

## Install

```npm
npm install vc-dialog --save
```

```html
//global varibale  vcdialog
<script src='../dist/vc-dialog.js'></script>
```

## Usage

## props

### okText

custom the ok dialog text.

* default: `确定`
* type: `String`

### cancelText

custom the cancel dialog text.

* default: `取消`
* type: `String`

### visiable

control the visiable of dialog.

* default: `false`
* type: `Boolean` 

### onOk | optional

the callback for onOk.

* type: `Function`

### onCancel | optional

the callback of onCancel

* type: `Function`


## example

* js

```js
import Vue from 'vue'
import {
        vcdialog
    } from '../dist/vc-dialog.js'

new Vue({
    el: '#app',
    data () {
        return {
            isShow: true,
            okText: 'ok',
            cancelText: 'cancel'
        }
    },
    components: {
        vcdialog
    },
    methods: {
        onOk () {

        },
        onCancel () {

        }
    },
    ready () {
    }
})
```

```vue
<vc-dialog 
    :visible='isShow'
    :okText='okText'
    :cancelText='cancelText'
    :onOk='onOk'
    :onCancel='onCancel'>
    <div class="your-html">
        
    </div>     
</vc-dialog>
```
