防止冒泡和捕获
	w3c的方法是e.stopPropagation()	ie的是e.cancelBubble=true
	
window.event? window.event.cancelBubble = true : e.stopPropagation(); 停止冒泡

取消默认事件
	w3c是e.prentDefault()  IE是e.returnValue=false
	
	if(e.preventDefault){
		e.preventDefault();
	}else{
		window.event.returnValue == false;
	}