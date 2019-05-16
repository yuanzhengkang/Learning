query与params都是在路由中传参
用法:
	query用path来引入  params只能用name来传递 不能使用path
展示效果 query像ajax中get请求(会在地址栏显示参数),而params更像post方式传递(不会在地址栏显示参数)

query传参
	this.$router.push({
		path:'***',
		query:{
			id:id		//这里是来传参的
		}
	}}
	接受参数
	this.$route.query.id
	
params传参
	this.$router.push({
		name:'***',
		params:{
			id:id		//这里是来传参的
		}
	})
	接收参数
	this.$route.params.id
	
传参是this.$router  接收参数是this.$route
$router是VueRouter的实例 想要跳到不同的URL可以使用$this.router.push / go / replace 去切换路由
$route是当前$router跳转对象。里面可以获取name path query params等相关信息