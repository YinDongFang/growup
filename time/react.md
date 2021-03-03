# 极客时间React学习笔记

## Flux单向数据流架构 vs MVC架构

### Flux

https://www.jdon.com/idea/flux.html

https://www.oschina.net/p/flux?hmsr=aladdin1e1

http://caibaojian.com/react/flux.html

#### Redux

http://www.ruanyifeng.com/blog/2016/09/redux_tutorial_part_one_basic_usages.html

https://www.redux.org.cn/

https://www.reduxjs.cn/

#### MobX

https://cn.mobx.js.org/

https://www.jianshu.com/p/2dfe11a9dfde

https://www.oschina.net/p/Mobx?hmsr=aladdin1e1

https://zhuanlan.zhihu.com/p/52502924

https://github.com/mobxjs/mobx

### 理论

1. 组件化思维
    - 以组件方式考虑UI构成
    - 单一职能原则
    - 复杂组件拆分小组件
    - 受控组件 / 非受控组件 逻辑梳理
    - 


### JSX vs 模板语法

JSX本质不是模板引擎，而是js语法糖，相比其他模板语法（解释器解释模板属性）更加灵活，可以和普通js代码混合使用：

- JSX作为表达式
- JSX标签属性中使用js表达式
- 对标签应用`...`扩展操作符
- 表达式作为JSX子元素

约定：

- 小写tag默认为html原生DOM节点
- 大写字母开头作为自定义节点
- JSX标记可以直接使用属性语法，如`<menu.Item />`
