路由传参
	通过this.$router.push({
		name:''/path:'',
		params:{
			
		}/
		query:{
			
		}
	})

父传子
	通过props传值  在父组件中定义属性名后边加上要传递的数据(记得绑定) 然后子组件中定义props属性 props里传父组件中定义的属性名  如父组件中<div :ops='ppp'></div> 子组件中接收props:['ops']

子传父
	this.$emit

组件之间传递  也就是同级传值
	使用本地存储可以达到
	建立公共通信组件，需要传值的组件引入该通信组件 在一个中绑定一个事件 this.on('eventname',this.id) 在另一个组件中触发事件this.$emit('eventname',(err)=>{}))