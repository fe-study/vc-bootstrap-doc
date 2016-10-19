---
title: vc-modal
type: components 
order: 20
---

* [online demo](https://iwaimai-bi-fe.github.io/vc-modal/examples/)
* [github](https://github.com/iwaimai-bi-fe/vc-modal)
* [npm](https://www.npmjs.com/package/vc-modal)
* [download](https://github.com/iwaimai-bi-fe/vc-modal/archive/master.zip)

## Install

``` npm
npm install vc-modal --save
```

``` js
// build version
import vcModal from 'vc-modal'

// recommend for *.vue project for small bundle size
import vcModal from 'vc-modal/src/Modal.vue'
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

### show

* require: `true`,
* type: `Boolean`,
* twoWay: `true`

### title

* type: `String`,
* default: `''`

### showCloseBtn

* type: `Boolean`,
* default: `true`

### maskCloseable

* type: `Boolean`,
* default: `true`

### showHeader

* type: `Boolean`,
* default: `true`

### showFooter

* type: `Boolean`,
* default: `true`

### width

* default: `null`

### top

* default: `null`

### center

* type: `Boolean`,
* default: `false`

### okText

* type: `String`,
* default: `'确定'`

### cancelText
    
* type: `String`,
* default: `'取消'`

### onOk

* type: `Function`

### onCancel

* type: `Function`

### effect

* type: `String`,
* default: `'fade'`

### backdrop

* type: `Boolean`,
* default: `true`

### large

* type: `Boolean`,
* default: `false`

### small

* type: `Boolean`,
* default: `false`

## example

* js

```js
import Vue from 'vue'
import vcModal from '../src'

new Vue({
    el: '#app',
    data () {
        return {
            bools: {
                'true': true,
                'false': false
            },
            title: 'title',
            show: true,
            center: false,
            small: false,
            large: true,
            showCloseBtn: true,
            showHeader: true,
            showFooter: true,
            effect: 'fade',
            width: '',
            top: '',
            okText: '确认',
            cancelText: '取消',
            maskCloseable: true
        }
    },
    components: {
        vcModal
    }
})
```

```html
<vc-modal
    :show.sync="show"
    :small="small"
    :title="title"
    :effect="effect"
    :center="center"
    :show-close-btn="showCloseBtn"
    :mask-closeable="maskCloseable"
    :show-header="showHeader"
    :show-footer="showFooter"
    :width="width"
    :top="top"
    :ok-text="okText"
    :cancel-text="cancelText"
    :on-ok="onOk"
    :on-cancel="onCancel"
>
    <div slot="modal-header" class="modal-header">
        content of header 
    </div>
    <div slot="modal-body" class="modal-body">
        content
    </div>
    <div slot="modal-footer" class="modal-footer">
        content of footer 
    </div>
</vc-modal>
```
