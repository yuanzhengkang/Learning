形成BFC
	float的值不为none
	overflow的值不为visible
	display的值不为table-cell table-caption inline-block中的任何一个
	position的值不为relative和static

BFC的规则
	BFC的元素布局是不受外界影响的(我们往往利用这个特性来消除浮动元素对其非浮动的兄弟元素和其子元素带来的影响) 
	并且在一个BFC中 块盒与行盒(行盒由一行中所有的内联元素所组成)都会沿着其父元素的边框排列