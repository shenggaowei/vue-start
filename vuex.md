# vuex

## 开始

1. Vuex 的状态存储是响应式的。当 Vue 组件从 store 中读取状态的时候，若 store 中的状态发生变化，那么相应的组件也会相应地得到高效更新。
2. 你不能直接改变 store 中的状态。改变 store 中的状态的唯一途径就是显式地提交 (commit) mutation。

## state

Vuex 通过 store 选项，提供了一种机制将状态从根组件“注入”到每一个子组件中（需调用 Vue.use(Vuex)），然后可在组件中通过 this.$store 访问到 store 中的状态

- mapState

```js
 computed: mapState({count : state => state.count})

 computed: mapState(['count'])

 computed: {...mapState({count: state => state.count})}
```

- mutation

最好提前在你的 store 中初始化好所有所需属性。mutation 是同步的，不能在其中执行异步代码

注意事项：
- 当需要在对象上添加新属性时，你应该
-  使用 Vue.set(obj, 'newProp', 123), 或者
- 以新对象替换老对象。例如，利用对象展开运算符 (opens new window)我们可以这样写：