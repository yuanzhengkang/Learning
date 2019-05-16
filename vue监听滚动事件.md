handleScroll() {
				let _this = this;	//为了再内部更好的获取this
				let scrollTop = document.documentElement.scrollTop //||document.body.scrollTop	//滚动条到顶部的位置
				let windowHeight = document.documentElement.clientHeight //|| document.body.clientHeight	//当前窗口内容可视区
				let scrollHeight = document.documentElement.scrollHeight// ||document.body.scrollHeight	//滚动条内容的总高度
				if(scrollTop+windowHeight >= scrollHeight - 1){				//滚动条到顶部的位置+当前窗口内容可视区 = 滚动条内容的总高度  因为有毫厘偏差所以-1会精确点  坏处就是持续加载
					let data = {
						merchantId: 14948,
						pageNum: _this.pageNum ++,				//page的第X页
						pageSize: 10,
						siteId: 51
					}
					this.$ajax.myOrder(data).then(res => {
						if (res.data.status.statusCode === 0) {
							res.data.result.list.forEach((item)=> {
								_this.divs.push(item)
							})
						}
					})
					
				}
			}
			
			
			
			window.addEventListener('scroll', this.handleScroll)		//监听this.handleScroll的滚动事件  