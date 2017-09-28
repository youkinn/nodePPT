title: 深入学习vue之数据响应与虚拟dom
speaker: yex
date: 2017-09-28
url: http://ppt.fed.tm
transition: cards
theme: dark

[slide]

# 深入学习vue（数据响应与虚拟dom）
## 演讲者：叶鑫

[slide]

# 回顾下几个概念

+ ## 数据驱动 {:&.rollIn}
+ ## 单向绑定
+ ## 双向绑定

[slide]

# 思考

+ ## 为何会出现数据绑定，它解决了哪些问题 {:&.rollIn}
+ ## 如何追踪数据的变化，如果自己实现会如何考虑

[slide]

# 观察者模式

+ 观察者模式（又被称为发布-订阅（Publish/Subscribe）模式，属于行为型模式的一种，它定义了一种一对多的依赖关系，让多个观察者对象同时监听某一个主题对象。这个主题对象在状态变化时，会通知所有的观察者对象，使他们能够自动更新自己。 {:&.rollIn}
+ 发布者发布数据，订阅者接收并处理数据。
+ 用观察者模式来实现一个简单的数据响应系统。
+ 看看Vue中如何实现

[slide]

# Vue中数据绑定的实现原理

+ ## Vue中实现了观察者模式。 {:&.rollIn}
+ ## 在Vue中，View（视图）是订阅者，Data(数据源)是发布者。数据发生变化后，通知视图更新(vm._update)。
+ ## Object.defineproperty是Vue实现观察者模式的关键。get收集订阅者，set发布数据更新通知(defineReactive)。

[slide]

# 虚拟DOM

+ ## 虚拟DOM是在什么样的情况下产生的 {:&.rollIn}
+ ## 想象一下，vue中的虚拟dom的结构是咋样的
+ ## 利用观察者模式追踪到数据的变化后，视图如何响应，过程是咋样的

[slide]

# 自己动手实现的话，如何考虑

[slide]

## Vue中虚拟DOM的实现原理

+ ## 用JS对象模拟DOM树(vm._render) {:&.rollIn}
+ ## 检测到数据变化后，生出一棵新的DOM树(vm._render)
+ ## 比较两棵虚拟DOM树的差异(vm.__patch__)
+ ## 把差异应用到真正的DOM树上(vm.__patch__)

[slide]

# 小结

+ ## 最终目的：最小化dom操作，提升性能 {:&.rollIn}

[slide]

# OVER