---
title: vc-card
type: components
order: 15
---

* [online demo](https://iwaimai-bi-fe.github.io/vc-card/examples/)
* [github](https://github.com/iwaimai-bi-fe/vc-card)
* [npm](https://www.npmjs.com/package/vc-card)
* [download](https://github.com/iwaimai-bi-fe/vc-card/archive/master.zip)

## Install


``` npm
npm install vc-card --save
```

``` js
// build version
import vcCard from 'vc-card'

// recommend for *.vue project for small bundle size
import vcCard from 'vc-card/src/Card.vue'
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

### title 

* type: `String`

### content

* type: `String`,

### bordered

* type: `Boolean`,
* default: `true`

### bodyClass

* type: `String`


## example

* js

```js
import Vue from 'vue'
import vcCard from '../src'

new Vue({
    el: '#app',
    data () {
        return {
            bools: {
                'true': true,
                'false': false
            },
            title: 'title',
            content: 'content',
            bordered: true,
            bodyClass: 'body-class'
        }
    },
    components: {
        vcCard
    }
})
```

```html
<vc-card
    :title="title"
    :content="content"
    :bordered="bordered"
>
    content
</vc-card>
```
