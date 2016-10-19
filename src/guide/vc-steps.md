---
title: vc-steps
type: components 
order: 30
---

* [online demo](https://iwaimai-bi-fe.github.io/vc-steps/examples/)
* [github](https://github.com/iwaimai-bi-fe/vc-tag)
* [npm](https://www.npmjs.com/package/vc-tag)
* [download](https://github.com/iwaimai-bi-fe/vc-tag/archive/master.zip)

## Install

``` npm
npm install vc-steps --save
```

``` js
// build version
import vcSteps from 'vc-steps'

// recommend for *.vue project for small bundle size
import vcSteps from 'vc-steps/src/Steps.vue'
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

* type: `Boolean`
* default: `true`
* twoWay: `true`

### steps

传入的steps，如果传入合法的 `allSteps` 预设，则会合并
    
* type: `Array`

### allSteps

- 可选的预设，多用于系统通用的流程，可传入通用预设
- 只有长度大于传入的`steps` 才会进行预设追加的合并

* type: `Array`

### title

* default: `'title'`

### subTitle

* default: `'subTitle'`

### closeable

* type: `Boolean`
* default: `true`

## example

* js

```js
import Vue from 'vue'
import vcTag from '../dist/build.js'

new Vue({
    el: '#app',
    data () {
        return {
            bools: {
                'true': true,
                'false': false
            },
            show: true,
            label: '我是标签1',
            size: 'default',
            status: 'success',
            disabled: false,
            closeable: true,
            onClose () {
                console.log('will close tag')
            },
            afterClose () {
                console.log('after close tag')
            }
        }
    },
    components: {
        vcTag
    }
})
```

```html
<vc-steps
    :show.sync="show"
    :steps="steps"
    :all-steps="allSteps"
    :title="title"
    :sub-title="subTitle"
    :closeable="closeable"
>
</vc-steps>
```
