sass的变量必须是$开头  后面紧跟变量名 而变量值和变量名之间就需要使用冒号(:)分隔开(就像css属性设置一样) 如果值后面加上!default则表示默认值

1.普通变量
	$fontSize:12px;
	body{
		font-size:$fontSize;			//就是font-size:12px的意思
	}
2.默认变量:Sass的默认变量仅需要在值后面加上!default即可
	$baseLineHeight: 2;
	$baseLineHeight: 1.5!default;
	body{
		line-height:$baseLineHeight;	//就是lineheight:2   这里不是默认值  默认变量的价值在进行组件化开发的时候会非常有用
	}
3.特殊变量:一般我们定义的变量都为属性值，可直接使用，但是如果变量作为属性或在某些特殊情况下等则必须要以#{$variables}形式使用
	$tops:top;
	$numbers:10;!default;
	
	body{
		border-#{$tops}{
			border-#{$tops}:1px solid $number+px;		//就是border-top：1px solid 10px;
		}
	}
4.多值变量：多值变量分为list类型和map类型，简单来说list类型有点像js中的数组，而map类型有点像js中的对象
	list
		list数据可通过空格，逗号或小括号分隔多个值，可用nth(var,var,index)取值。list数据操作还有很多其他函数如：
		length($list)
		join(list1,list1,list2,[$separator])
		append(list,list,value,[$separator]) 具体可参考sass Functions（搜索List Functions即可）
		
		$linkColor:#08c #333 !default;//第一个值为默认值，第二个鼠标滑过值
		a{
		  color:nth($linkColor,1);    //就是第一个颜色 
		  &:hover{
			color:nth($linkColor,2);	//第二个颜色
		  }
		}
		
		map
			map数据以key和value成对出现，其中value又可以是list
			格式为：$map: (key1: value1, key2: value2, key3: value3)
			通过map-get(map,map,key)取值
			关于map数据还有很多其他函数如map-merge(map1,map1,map2)，map-keys(map)，map−values(map)，map−values(map)等
			具体可参考sass Functions（搜索Map Functions即可）
			
			$key-green:green;
			$val-green:#fff;
			$key-red:red;
			$val-red: #ff0000;
			$key-info:info;
			$val-info: #ff00ff;
			$key-success:success;
			$val-success: #f66;

			//$text: (green: #fff, red: #ff0, info: #f0f);
			$text: (
				$key-green: $val-green,	//将绿色编码赋值给green
				$key-red: $val-red,		//将红色编码赋值给red
				$key-info: $val-info,	//将info编码赋值给info
				$key-success:$val-success	//将success编码赋值给success
			);

			@each $i, $size in $text {		//$i表示$text中的前缀   $size表示$text中的后缀 颜色编码
				.text-#{$i} {
					color: $size;
				}
			}
全局变量：在变量值后面加上!global即为全局变量。这个目前还用不上，不过将会在sass 3.4后的版本中正式应用。目前的sass变量范围饱受诟病，所以才有了这个全局变量。
	目前变量机制 在选择器中声明的变量会覆盖外面全局声明的变量。(这也就人们常说的sass没有局部变量)
	$fontSize:12px;
	body{
		$fontSize: 14px;
		font-size:$fontSize;	//输出14
	}
	p{
		font-size:$fontSize;	//输出12   因为上边块域内声明的fontSize是局部变量  只有设置了!global之后才会称为全局变量
	}
	