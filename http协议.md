特点
	简单快速 每个uri都是固定的
	灵活 通过一个http类型 可以完成不同数据类型的传递
	无连接 连接一次会断掉 不会保持链接
	无状态 没有记录状态 无法区分两次连接的身份
http方法
	get	获取资源
	post	传输资源
	put	更新资源
	delete	删除资源
	head	获得报文头部
post和get的区别
	get在浏览器回退的时候是无害的 而post会再次提交请求
	get产生的url地址可以被收藏 post不可以
	get只能进行url编码 而post支持多种编码方式
	get请求参数可以被完整保存在浏览器历史记录里，post参数不可以
	get请求在url中传送的参数是有长度限制的 post没有限制
	参数的数据类型，get只接受ASCLL字符 post没有限制
	get比post更不安全 因为参数暴露在url上
	get参数通过url传递 post放在request body中
	
http与https的区别
	https比http更安全
	https有ssl证书 http没有
	https地址栏前方有绿色安全锁 http没有
	http是明文传输协议 https是加密传输协议
	http端口是80 https端口是443
	