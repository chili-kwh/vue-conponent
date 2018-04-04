# vue-demo

> A Component Demo Based on Vue.js

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

# Input


## API



| 属性   | 说明      |   类型   |   默认值   |  可选值 |
| :-------- | ------ | :----: | :-----: | :-----: |
| type | Input类型 | string | text | text/textarea |
| value | 绑定值 | string / number | － | － |
| v-model | 双向绑定变量 | string | － | － |
| placeholder | 输入框占位文本	 | string | '输入内容' | － |
| readonly | 是否只读 | boolean | － | false |
| maxLength | 最大输入长度 | number | null | － |
| env | 当前环境（值为dev时测试双向绑定）| string | － | dev |

| **slot** |  |
| :-------- | ------ |
| name |  |
| prepend | 输入框头部内容 |  |

| **event** |  |  |
| :-------- | ------ |:-----: |
| 事件名称	 | 说明 | 	回调参数 |
| change | 在 Input 值改变时触发	 | (value: string / number) |
| enter | 按下回车键触发 | (event: Event) |

