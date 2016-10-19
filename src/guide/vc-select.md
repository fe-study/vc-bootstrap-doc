---
title: vc-select
type: components 
order: 12
---

* [online demo](https://iwaimai-bi-fe.github.io/vc-select/examples/)
* [github](https://github.com/iwaimai-bi-fe/vc-select)
* [npm](https://www.npmjs.com/package/vc-select)
* [download](https://github.com/iwaimai-bi-fe/vc-select/archive/master.zip)

## Install

``` npm
npm install vc-select --save
```

``` js
// build version
import vcSelect from 'vc-select'

// recommend for *.vue project for small bundle size
import vcSelect from 'vc-select/src/Select.vue'

// and get the child component
const vcOption = vcSelect.vcOption
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

组件名称，也是DOM的name属性,默认随机生成
    
* type: String,
* default: `vc-select-${Date.now()}`

### label

项目说明文案

* type: `String`

### value

对外暴露的值

* twoWay: `true`,
* type: `Array | String | Number` 内部会记录下初始化类型快照，用于反同步，只区分Array, 非Array

### tags

* type: `Boolean`,
* default: `false`

### placeholder

占位提示

* type: `String`
* default: `'没有选择'`

### disabled

是否不可用
    
* type: `Boolean`,
* default: `false`

### readonly

是否只读

* type: `Boolean`,
* default: `false`

### options

选项: Array是目标类型，Object也支持转换，但是Array必须为Array<Object{ value: label }>

* type: `Array | Object`

### lazy

用于区分下拉选择的值的同步模式(时机)

* type: `Boolean`,
* default: `false`

### multiple

是否可多选

* type: `Boolean`,
* default: `false`

### searchable

是否可搜索，只有在 `options` 提供才可以

* type: `Boolean`,
* default: `false`

### limit

最多选择多少项

* type: `Number`,
* default: `1024`

### closeOnSelect

选择后自动关闭下拉,仅作用在单选

* type: `Boolean`,
* default: `false`

### width

选择按钮宽度，不包括label部分 

* type: `Number | String`,
* default: `'200'`

### height

下拉列表高度

* type: `Number | String`,
* default: `'400'`

### showSelectAllOption

是否显示'全部'选项

* type: `Boolean`,
* default: `false` 

### selectAllOptionLabel

全选的文案

* type: `String`,
* default: `'全部'`

### selectAllOptionValue

重要! 传给后端的key值，有默认值，初始化传入自动全选，可配置来避免冲突

* type: `String`,
* default: `'__all__'`

### selectAllBehavior

是全部选项被选中还是语义上选中前后端约定的key，默认是全部选中

* type: `String`,
* default: `'allChecked'` // ['allChecked', 'semantic'] 全选行为上可以是真正全部选项选中或语义上的选中'全部'这一项

### mutual

选择了其他又选择了全部选项，则清空其他，只显示全部, 即全部与其他选项互斥,使得行为更清晰

* type: `Boolean`,
* default: `true`

### dispatchArgs

要对外派发的数据

* type: `Array`

### onShow

* type: `Function`

### onHide

* type: `Function`

### onSelect
* type: `Function`

## example

* js

```js
import Vue from 'vue'
import vcSelect from '../src/Select'

const vcOption = vcSelect.vcOption

new Vue({
    el: '#app',
    data () {
        return {
            bools: {
                'true': true,
                'false': false
            },
            name: 'name',
            width: '300',
            height: '300',
            label: 'label',
            placeholder: 'placeholder',
            options: {
                '0': '徐州',
                '1': '北京',
                '2': '上海',
                '3': '广州',
                '4': '深圳',
                '6': '沈阳',
                '7': '苏州',
                '8': '无锡',
                '9': '南京',
                '10': '镇江',
                '11': '南通',
                '12': '宿迁',
                '13': '连云港',
                '14': '常州',
                '15': '盐城'
            },
            lazy: false,
            value: '',
            multiple: true,
            searchable: true,
            cos: true,
            showSelectAllOption: true,
            selectAllOptionValue: '__all__',
            selectAllOptionLabel: '全部',
            selectAllBehavior: 'allChecked',
            tags: true
        }
    },
    created () {
        let href = location.href
        let p = parseURL(href)
        let type = p.params.type || 'array'
        let value = p.params.value || this.selectAllOptionValue 
        if (type.toLowerCase() === 'array') {
            this.value = [value]
        } else {
            this.value = value
        }
    },
    components: {
        vcSelect,
        vcOption
    }
})
```

```html
<vc-select
    :tags="tags"
    class="vc-select"
    :lazy="lazy"
    :width="width"
    :height="height"
    :name="name"
    :label="label"
    :placeholder="placeholder"
    :options="options"
    :value.sync="value"
    :multiple="multiple"
    :searchable="searchable"
    :close-on-select="cos"
    :show-select-all-option="showSelectAllOption"
    :select-all-option-value="selectAllOptionValue"
    :select-all-option-label="selectAllOptionLabel"
    :select-all-behavior="selectAllBehavior"
    :on-show="onShow"
    :on-hide="onHide"
    :on-select="onSelect"
>
</vc-select>
```
