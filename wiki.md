## why？ 为什么要选这个主题
醉染比较简单 但其实大部分时候我们都对这些配置项有点云里雾里，一写配置项还会出现混淆的情况
所以借这个机会做个总结吧



## what？ 配置项简介
### env
指定环境，决定了当前环境下可使用的全局变量
* browse
* es6 - 允许使用ES6中esm之外所有的 new ES6 global variables
* node
* commonjs

### globals
声明全局变量；如果在项目中一个文件里使用到了这个文件内没有定义的全局变量，ESlint 会进行报错。


### parser - 解析器
解析我们的代码，生成AST；常用的解析器：
* Esprima（默认）
* Babel-ESlint
* @typescript-eslint/parser


### parserOptions
ESlint 默认解析 ES5 语法，通过配置 parserOptions，可以覆盖这个设置从而解析其他 ES 版本 或者是 JSX 语法
* ecmaVersion - 3、5（默认）、6、7、8、9等，也可以写 2015（6）、2016（7）等，也可以使用 latest 表示使用最新的ecma版本
* sourceType - 模块类型
    * script（默认）
    * module - 使用esm
* ecmaFeatures - 使用额外的语言特性
    * globalReturn - 允许在全局使用 return 语句
    * impliedStrict - 允许全局使用 strict 模式
    * jsx - 使用jsx


### settings
可以在settings里声明一些数据，这些数据在执行rules的时候可以拿到，这在写定制插件的时候比较有用

### root
指定当前配置文件作用于整个项目

### extends
顾名思义，可以看做是去继承一个个配置方案的最佳实践(它配置的内容实际就是一份份别人配置好的.eslintrc.js)
虽然说需要根据不同的需求、风格、规范去配置不同的eslint规则，但往往相似的项目之间需要配置的规则都是大同小异的。如果每一个项目都是重新一步步开始选择配置规则就比较显得不太人性了；这个时候就是extends体现作用的时候
eg. 
```js
    // 1 - 继承 eslint-plugin-demo 插件导出的config1配置  2- 继承 eslint-config-airbnb 导出的配置
    extends: [ 'plugin:demo/config1' , 'airbnb' ],
    extends: [ 'plugin:eslint-plugin-demo/config1' , 'eslint-config-airbnb' ]

```

### plugins
我理解插件就是一个包含了多条规则rules的容器，我们配置了 plugins 就表明我们接下来可以用插件里面的rules来检查我们的代码； eg.
```js
    plugins: ['react'],
    plugins: ['eslint-plugin-react']
```
以上配置表明我们可以用 eslint-plugin-react 插件里的规则了，具体规则的开启关闭我们可以在rules里面去配置


### rules

### overrides
对特殊的文件进一步配制对应的lint规则



## diff 对比 extends plugin rules





## how？ 如何开发一个插件





## 如何写一个rule




