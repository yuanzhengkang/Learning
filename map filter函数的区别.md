map() 会根据提供的函数对指定序列做映射  
第一个参数function以参数序列中的每一个元素调用function函数 返回包含每次function函数返回值的新列表


filter() 函数用于过滤数列 过滤掉不符合条件的元素 返回由符合条件元素组成的新列表
接收两个参数 第一个为函数 第二个为序列，序列的每个元素作为参数传递给函数进行判断 然后返回true或false 最后将返回true的元素放到新列表中


function fn(res) {
				if (res % 2 == 0) {
					return true
				}
				return false
			}
			
			let i = [1,2,3,4,5,6,7,8,9]
			let filters = i.filter(fn);
			let maps = i.map(fn)
			console.log(maps)
			console.log(filters)
			
			
			就是filter会把符合筛选条件的留下  map会将所有数据都遍历一遍 返回包含每个值得新值  也就是说 map返回得新值是你return的值