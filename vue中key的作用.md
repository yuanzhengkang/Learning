vue实现了一套虚拟DOM 让我们不可以直接操作DOM元素 只操作数据即可重新渲染页面 隐藏在背后的原理就是其高效的Diff算法
当页面的数据发生变化的时候，Diff算法只会比较同一层级的节点
如果节点类型不同的 直接干掉前面的节点 再创建并插入新的节点 不会再比较这个节点以后的子节点了
如果节点类型相同 则会重新设置该节点的属性 从而实现节点的更新

所以一句话说 key的作用主要是为了高效的更新虚拟DOM 另外在vue中使用相同标签名元素的过滤切换时 也会使用到key属性 其目的是为了让vue可以区分他们 
否则vue只会替换其内部属性而不会触发过滤效果