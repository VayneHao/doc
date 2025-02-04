[学习文档](https://www.redux.org.cn/)

## 介绍

redux 是一个应用数据流框架，主要是解决了组件间状态共享的问题，原理是集中式管理，主要有三个核心方法，
action，store，reducer，工作流程是 view 调用 store 的 dispatch 接收 action 传入 store，reducer 进行 state 操作，view 通过 store 提供的 getState 获取最新的数据。

新增 state,对状态的管理更加明确，通过 redux，流程更加规范了，减少手动编码量，提高了编码效率，同时缺点时当数据更新时有时候组件不需要，但是也要重新绘制，有些影响效率。一般情况下，我们在构建多交互，多数据流的复杂项目应用时才会使用它们

## 三大原则

1.单一数据源。整个应用的 state 被存储在一个 object tree 中，并且这个 object tree 只存在于唯一一个 store
2.state 是只读的。唯一改变 state 的方法就是触发 action,action 是一个用于描述已发生事件的普通对象。不能随意修改 state，为了保证数据来源的可靠。 3.使用纯函数来执行修改。

## redux 有什么缺点

一个组件所需要的数据，必须由父组件传过来，而不能像 flux 中直接从 store 取。
当一个组件相关数据更新时，即使父组件不需要用到这个组件，父组件还是会重新 render，可能会有效率影响，或者需要写复杂的 shouldComponentUpdate 进行判断。
