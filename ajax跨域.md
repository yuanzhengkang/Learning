JSONP
	JSONP是通过在script标签中访问不同域的URL实现跨域，不过只能get请求一般不用

代理的方式
	服务器A的test01.html页面想访问服务器B的后台action，返回‘test’字符串，此时就会出现跨域请求，浏览器控制台会出现报错提示，由于跨域是浏览器的同源策略造成的，返回服务器后台不存在该问题
	可以在服务器A中添加一个代理action，在该action中完成对服务器B中action数据的请求，然后在返回到test01.html页面

CORS
	添加响应头，允许跨域
		跨域发送ajax请求的时候，请求头中会自带一个字段withCredentials:true 这个字段会发送身份信息到服务端 如ssl cookie 然后在浏览器中设置请求头
		addHeader('Access-Control-Allow-Origin:*')  允许所以来源访问
		addHeader('Access-Control-Allow-Method:post/get')	允许请求的类型
