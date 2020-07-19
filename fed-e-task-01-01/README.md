选择题：

1、下面关于虚拟 DOM 的说法正确的是（BCD）

A. 使用虚拟 DOM 不需要手动操作 DOM，可以极大的提高程序的性能。

B. 使用虚拟 DOM 不需要手动操作 DOM，可以极大的提高开发效率。

C. 虚拟 DOM 可以维护程序的状态，通过对比两次状态的差异更新真实 DOM。

D. 虚拟 DOM 本质上是 JavaScript 对象，可以跨平台，例如服务器渲染、Weex 开发等。

2、下面关于 Snabbdom 库的描述错误的是（CD）

A. Snabbdom 库是一个高效的虚拟 DOM 库，Vue.js 的虚拟 DOM 借鉴了 Snabbdom 库。

B. 使用 h() 函数创建 VNode 对象，描述真实 DOM 结构。

C. Snabbdom 库本身可以处理 DOM 的属性、事件、样式等操作。

D. 使用 patch(oldVnode, null) 可以清空页面元素

简单题：

打补丁，把新节点中变化的内容渲染到真实 DOM ，最后返回新节点作为下一次处理的旧节点。

- 对比新旧 Vnode 是否是相同节点（节点的 key 和 sel 相同）
- 如果不是同节点，删除之前的内容，重新渲染
- 如果是相同节点，在判断新的 VNode 是否有 text ，如果有并且和 oldNode 的 text 不同，直接更新文本内容
- 如果新的 VNode 有 children ，判断子节点是否有变化，判断子节点的过程使用的就是 diff 算法
- diff 过程只进行同层级比较