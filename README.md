# 说明 - 请必看

> 该库fork自[https://github.com/HcySunYang/vue-design](https://github.com/HcySunYang/vue-design)，由于原库已经不是主干分支，但是个人觉着对于对于了解`Vue2`还是很有帮助的，就自己部署了一份

**这套文章不再维护**

相信大家会有些许疑问，诸如：为什么不维护了？为什么不从一而终？

我来解释一下，先说一下是否存在**不从一而终**：不存在。那为什么不继续写完呢？并不是不想完成，而是有了更好的选择，我在写一套新的文章：`《Vue3框架设计精髓》`，这个决定有以下几点原因。

- 1、围绕 `Vue3`

你没看错，新的文章将围绕 `Vue3` 讲解，这套文章的目的只有一个：**站在框架设计者的角度，从零实现一个五脏俱全的 `Vue3`**。众所周知，今年 `Vue3` 会对外公布，但具体什么时间不确定，所以新的文章会随着 `Vue3` 的公布而公开。

- 2、授人以渔

现有的这套文章，以”逐行级别“为卖点，但实则过于冗余，而且不突出核心思想。新的文章将站在对”框架设计“这个更加高层次的理解之上所编写的，准确的说，新的文章将不再是源码分析、不再是源码分析、不再是源码分析(重要的事儿我想说三百遍)，而是让读者站在框架设计者的角度思考问题。在文章中，我会抛出问题所在，思考差点什么，提出解决方案，最终编码实现。这么做的好处是：突出核心思想，授人以渔。我不会在文章中贴出 `Vue3` 的代码，但如果你认为这套文章的编码实现与真正 `Vue3` 的实现之间存在“差距”从而误导你，那你就多虑了，这是因为这套文章所讲的一切内容都不是我凭空创造的，而是基于 `Vue3` 的实现来讲解的，只不过你感觉不到这些，还是那句话：**这套文章的视角是“第一人称”，读者的角度是框架的设计者**，所以你完全可以给这套文章起一个很俗气的名字，例如：《一起撸一个 Vue3》之类的，这带来了另外一个好处：**即使你没用过 `Vue3`，依然能够看得懂文章**。

- 3、真正的不会过时

实际上，现有文章的讲解方式本质上是”贴源码的讲解方式“，所以一旦文章不更新，源码又总是再变，那么文章就总是会过时。而新的文章本质上不依赖 `Vue3` 的源码，而是借鉴 `Vue3` 的思想编写的一套文章，如果你掌握了 `Vue3` 的核心设计原则，那么代码变动是影响甚微的。再说一次：**你只需要掌握核心设计原则**。

- 4、提供完整的可执行代码&在线体验地址

众所周知 `Vue3` 采用 `TS` 编写，但新的文章中所有的代码都使用 `JavaScript`，所以你即使看不懂 `TS` 也能看得懂这套文章。当然带来的弊端就是文章中体现不出 `Vue3` 在 `TS` 类型系统上的设计，但好处是这让我编写可执行代码和在线体验案例时方便了许多，在这套文章中的每一个小结，几乎都提供了与之相符的可执行代码和在线体验地址，让你在学习的过程中感觉很实在。

来看一下整体的目录大纲吧：

- 一、组件的本质
	1. 组件的产出是什么
	2. 组件的 VNode 如何表示
	3. 组件的种类
- 二、先设计 VNode 吧
	1. 用 VNode 描述真实 DOM
	2. 用 VNode 描述抽象内容
	3. VNode 的种类
	4. 使用 flags 作为 VNode 的标识
	5. 枚举值 VNodeFlags
	6. chidlren 和 ChildrenFlags
	7. VNodeData
- 三、辅助创建 VNode 的 h 函数
	1. 在 VNode 创建时确定其类型 - flags
	2. 在 VNode 创建时确定其chidlren的类型
	3. 使用 h 函数创建 VNode
- 四、渲染器之挂载
	1. 责任重大的渲染器
	2. 挂载普通标签元素
		- 2.1、基本原理
		- 2.2、class的处理
		- 2.3、Attributes 和 DOM Properties
		- 2.4、事件的处理
	3. 挂载纯文本、Fragment 和 Portal
		- 3.1、挂载文本节点
		- 3.2、挂载 Fragment
		- 3.3、挂载 Portal
	4. 有状态组件的挂载和原理
	5. 函数式组件的挂载和原理
- 五、渲染器之patch
	1. 基本原则
	2. 替换 VNode
	3. 更新标签元素
		- 3.1、更新标签元素的基本原则
		- 3.2、更新 VNodeData
		- 3.3、更新子节点
	4. 更新文本节点
	5. 更新 Fragment
	6. 更新 Portal
	7. 有状态组件的更新
		- 7.1、主动更新
		- 7.2、初步了解组件的外部状态 props
		- 7.3、被动更新
		- 7.4、我们需要 shouldUpdateComponent
	8. 函数式组件的更新
- 六、渲染器的核心 Diff 算法
	1. 核心 Diff 算法的发展史
	2. React 的核心 Diff 算法原理
	3. Vue2 的核心 Diff 算法原理
	4. Vue3 所采用的核心 Diff 算法及原理
		- 4.1、相同的前置和后置元素
		- 4.2、移动次数总是最少的
		- 4.3、最长递增子序列
- 七、自定义渲染器和异步渲染
	1. 自定义渲染器的原理
	2. 异步渲染的意义
	3. 异步渲染的关键点
	4. 调度器的实现
	5. 基于调度器的异步渲染
- 八、有状态组件的设计
	1. 组件自身状态
	2. 组件的外部状态
	3. 插槽的本质
	4. 组件的生命周期
	5. ref 的实现
	6. 一个组件涉及多个VNode对象
	7. 如何建立组件的父子关系
	8. 事件系统
	9. 兼容Vue2的对象式组件
- 九、基于 Proxy 的响应系统
	1. 基本原理
	2. 对象和数组的代理
	3. 集合的代理
	4. 计算属性
	5. Watch 的实现
	6. 组件实例的访问代理
- 十、组件的拓展
	1. 异步组件
	2. 指令的实现
	3. 实现 keepAlive
	4. memoize 的意义和实现
	5. Vue 中复用逻辑未必需要 hooks
	6. 错误处理


以上。

# 下面为原文

## 文章特点

* 超级详细 - 逐行级别的分析

所谓逐行并非一行接着一行，逐行指的是讲解的详细程度，这套文章将致力于覆盖所有核心代码，毕竟每一句代码都有他存在的意思，假如我们不讲明白任何一句代码的意义，那又怎么敢说是源码分析呢？

* 实时更新 - 与 `Vue` 源码 `dev` 分支保持同步

这套文章的特点之一就是**永远不会过时**，因为我们会跟随 `Vue` 源码 `dev` 分支的脚步更新文章的内容，这对于读者来讲的好处是学习的总是最新的。（注：有的时候 `dev` 分支的更新到文章的更新会有稍许延迟）。

这里要解释一下，有的时候我们在讲解一个文件的代码时，你会发现，有些内容我们并没有进行讲解，那是因为这部分内容可能与本节的主题无关，但这些内容绝对不会被遗漏，它们会被放到合适的地方进行讲解

* 深度分析 - 讲解issue

我们知道 `Vue` 这个项目自诞生以来一直都在不断的更新完善，比如添加新的特性，修复已知bug等等。而在这个过程中源码也将越来越完善，这也意味着代码曾经并不完善，本套文章在分析源码时除了告诉你这段代码为什么这么写之外，还会根据相关 `issue` 分析这段代码之前是怎么写的以及存在的问题。

## 为什么要阅读源码？

如果你要问我这个问题，我会反问你：为什么要读书(技术书)？不知道你对这句话怎么看：**源码难道不是更精华的书吗？**

## 你应该了解的

文章将会尽可能详细，且尽可能对基础的知识点进行讲解，但需要太多口舌的东西即使再基础也不会去讲，这里列出我希望你在阅读该系列文章前最好了解的东西：

* ES6+
* node & npm & package.json
* Rollup（这东西要比webpack容易上手的多）
	* [英文文档](https://rollupjs.org/)
* flow（类型检查）
	* [flow](https://flow.org/en/)

由于 Vue 的源码采用 ES6，所以你至少应该掌握 ES6 才能看得懂，其次你最好对 `package.json` 中的字段的作用有所了解。由于 Vue 使用 `Rollup` 构建，所以你不了解 `Rollup` 的话，你就看不懂 Vue 的构建配置，最后 Vue 采用 `flow` 做类型系统，最起码就应该知道 `flow` 的简单语法，否则会影响你看源码。

## 推荐阅读这套文章的方式

既然是阅读源码，没有源码怎么读？所以你要使用你喜欢的方式拿到源码才行，最简单的方式是，clone 一份源码到你的本地。如果你不想这么做，你可以安装一个 `chrome` 的扩展程序，使得你能够以在线以资源管理器的方式阅读GitHub仓库的代码，我常用的 `chrome` 扩展是：[octotree](https://github.com/buunguyen/octotree)，类似的扩展还有很多，你喜欢就好。

## 一点补充

有的同学可能会有疑问，比如：*你又不是作者本人，你怎么知道人家的代码为什么那么写*、*Vue.js又不是你写的，谁知道你分析的对不对* 等等。

对于第一个问题我想说的是，你们的怀疑是对的，毕竟最有权威分析 `Vue` 源码的人必然是作者本身，但同学们要知道**作者(小右)才没有时间来给大家写一套源码分析的文章**。对于第二个问题，`Vue` 确实不是我写的，但为了证明这套文章还是稍微有点质量的，在这里我把看源码过程中提过的一些 `PR` 贴在下面，也证明我确实对 `Vue` 有些粗浅的理解。

* [https://github.com/vuejs/vue/pull/7981](https://github.com/vuejs/vue/pull/7981)
* [https://github.com/vuejs/vue/pull/6795](https://github.com/vuejs/vue/pull/6795)
* [https://github.com/vuejs/vue/pull/7875](https://github.com/vuejs/vue/pull/7875)
* [https://github.com/vuejs/vue/pull/6833](https://github.com/vuejs/vue/pull/6833)
* [https://github.com/vuejs/vue/pull/7308](https://github.com/vuejs/vue/pull/7308)
* [https://github.com/vuejs/vue/pull/7762](https://github.com/vuejs/vue/pull/7762)
* [https://github.com/vuejs/vue/pull/7510](https://github.com/vuejs/vue/pull/7510)
* [https://github.com/vuejs/vue/pull/8734](https://github.com/vuejs/vue/pull/8734)

说实话，上面的 `PR` 都是些微不足道的，因为写文章需要大量的时间，随着这些文章的完成，我很希望抽出时间做一些实质性的贡献。
