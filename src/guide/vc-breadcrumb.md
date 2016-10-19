---
title: vc-breadcrumb
type: components
order: 28
---

* [online demo](https://iwaimai-bi-fe.github.io/vc-breadcrumb/examples/)
* [github](https://github.com/iwaimai-bi-fe/vc-breadcrumb)
* [npm](https://www.npmjs.com/package/vc-breadcrumb)
* [download](https://github.com/iwaimai-bi-fe/vc-breadcrumb/archive/master.zip)

## Install

``` npm
npm install vc-breadcrumb --save
```

``` js
// build version
import vcBreadcrumb from 'vc-breadcrumb'

// recommend for *.vue project for small bundle size
import vcBreadcrumb from 'vc-breadcrumb/src/Breadcrumb.vue' 
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

### routes

* type: `Array`,
* default: `[]`

### separator

* default: `'/'`

### `Breadcrumb-item` prop

### text: 

* type: `String`

### url
* type: `String`

## example

* js

```js
import Vue from 'vue'
import vcBreadcrumb from '../src'

const { vcBreadcrumbItem } = vcBreadcrumb

var vcSeparator = Vue.extend({
    template: '<span class="separator-class">-/-</span>'
})

new Vue({
	el: '#app',
	components: {
        vcBreadcrumb,
        vcBreadcrumbItem,
        vcSeparator
	},
	data () {
		return {
            defaults: false,
            separator: '/',
            routes: [{
                url: 'https://github.com/IndexXuan/',
                text: 'IndexXuan'
            }, {
                url: 'https://github.com/stars',
                text: 'stars'
            }, {
                text: 'current'
            }]
		}
	}
})
```

```html 
<vc-breadcrumb
    :routes="routes"
    :separator="separator"
>
</vc-breadcrumb>

<vc-breadcrumb
    :routes="routes"
    :separator="separator"
>
    <vc-separator slot="separator"></vc-separator>
</vc-breadcrumb>

<vc-breadcrumb 
    :separator="separator"
>
    <vc-breadcrumb-item url="https://github.com/IndexXuan">首页</vc-breadcrumb-item>
    <vc-breadcrumb-item>第二级</vc-breadcrumb-item>
    <vc-breadcrumb-item>第三级</vc-breadcrumb-item>
</vc-breadcrumb>

<vc-breadcrumb 
    :separator="separator"
>
    <vc-breadcrumb-item url="https://github.com/IndexXuan">
        首页
        <vc-separator slot="separator"></vc-separator>
    </vc-breadcrumb-item>
    <vc-breadcrumb-item>
        第二级
        <vc-separator slot="separator"></vc-separator>
    </vc-breadcrumb-item>
    <vc-breadcrumb-item>
        第三级
        <vc-separator slot="separator"></vc-separator>
    </vc-breadcrumb-item>
</vc-breadcrumb>
```
