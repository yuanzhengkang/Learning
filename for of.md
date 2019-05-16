for of	和 for in都是循环所有数据  跟for in的区别就是for of无法遍历对象
for of 用法
	let item = [1,2,3,4]
	for(let i of item){
		console.log(item,i) item是数组  i是数据
	}
	for(let i in item){
		console.log(item,i)
	}