# UNI-APP 生命周期执行顺序


## 应用生命周期

[官方文档](https://uniapp.dcloud.net.cn/collocation/App.html#applifecycle)


```
App 在App.vue中定义
// 应用初始化完成触发，全局只触发一次，可做登录判断...
onLaunch
// 应用启动的时候，或者从后台进入前台就会触发
onShow
// 应用从前台进入后台就会触发
onHide

```

## 页面生命周期

```
page 在页面中都可以定义
// 监听页面加载，在开始加载的时候触发，元素还未开始渲染 -- 页面只执行一次  tab页面不加载
onLoad
// 监听页面显示，每次页面出现的时候，就会触发这个钩子。
onShow
// 监听页面渲染完成， 如果页面渲染速度快(元素太少)，会在页面翻页动画完成前就触发了 -- 页面只执行一次
onReady
// 监听页面隐藏，每次页面隐藏的时候，就会触发这个钩子。 页面跳转会触发
onHide
// 监听页面卸载 重定向跳转页面会触发
onUnload


```


## 组件的生命周期
```

component 组件中使用
// 在实例初始化之后被调用
beforeCreate
// 在实例创建完成后被立即调用--调函数
created
// 在挂载开始之前被调用
beforeMount
// 挂载到实例上去之后调用
mounted
// Vue 实例销毁后调用
destroyed

```

## 生命周期执行顺序
```

// 进入应用
App Launch
App Show
page onLoad
page onShow
component beforeCreate
component created
component mounted
page onReady

// 应用后台
App Hide
page onHide

// 应用关闭
page onUnload
component destory

// 后台重新进入
App Show
page onLoad
page onShow

```
