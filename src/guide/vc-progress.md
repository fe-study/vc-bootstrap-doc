---
title: vc-progress
type: components
order: 25
---

* [online demo](https://iwaimai-bi-fe.github.io/vc-progress/examples/)
* [github](https://github.com/iwaimai-bi-fe/vc-progress)
* [npm](https://www.npmjs.com/package/vc-progress)
* [download](https://github.com/iwaimai-bi-fe/vc-progress/archive/master.zip)

## Install

``` npm
npm install vc-progress --save
```

``` js
// build version
import vcProgress from 'vc-progress'

// recommend for *.vue project for small bundle size
import vcProgress from 'vc-progress/src/Progress.vue'
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

* type: `Number | String`,
* required: `true`

### showProgress

* type: `Boolean`,
* default: `true` 

### type

* type: `String`

### striped

* type: `Boolean`,
* default: `false`

### animated

* type: `Boolean`,
* default: `false`

## example

* js

```js
import Vue from 'vue'
import vcProgress from '../src'

new Vue({
    el: '#app',
    data () {
        return {
            bools: {
                'true': true,
                'false': false
            },
            value: 80,
            showProgress: true,
            type: 'success',
            striped: true,
            animated: true
        }
    },
    components: {
        vcProgress
    }
})
```

```html
<vc-progress
    style="border-radius: 5px;"
    :value="value"
    :type="type"
    :show-progress="showProgress"
    :animated="animated"
    :striped="striped"
>
</vc-progress>
```
