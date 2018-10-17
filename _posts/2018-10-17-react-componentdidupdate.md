---
layout: post
title:  "React生命周期之ComponentDidUpdate"
date:   2018-10-17 10:20:40 +0800
categories: react
---


今天使用 componentWillReceiveProps，始终都不能获取到 props 更新后的正确状态，后来查阅 API，改成了 componentDidUpdate ，获取到了正常的数据。

为什么？

## componentWillReceiveProps

在[官方文档](https://reactjs.org/docs/react-component.html#componentdidupdate)中，componentWillReceiveProps 是一个 unsafe 的方法，并且给出了相关的解释：

> 在组件 props 变化时，会调用该方法

> 使用这个生成周期方法会经常导致 bug，所以在未来会被抛弃。

> 如果你需要执行一个改变 props的副作用的请求，使用 componentDidUpdate 生命周期代替

以上，看来在代码中应该尽量少用这个方法了。

## componentDidUpdate

> componentDidUpdate() 在更新发生后立即调用。这个方法在初始的 render() 时不会被调用。

> 在发送网络请求后，比较 previous props 和 current props 的好地方

