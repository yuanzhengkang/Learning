keep-alive是vue提供的一个抽象的组件，用来对组件进行缓存，从而节省性能 由于是一个抽象组件 所以在vue页面渲染完毕之后不会被渲染成一个DOM元素
当组件在keep-alive中被切换时组件的activated deactivated这两个生命周期钩子函数会被执行

被keep-alive包裹的组件状态会被保留 假如我们将某个列表页滑动到一定的位置  切换走再切换回来会发现位置会在上次离开的位置