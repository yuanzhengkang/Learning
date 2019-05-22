fetch是基于promise设计的 fetch是原生js

他比axios ajax简洁  脱离了xhr 是es规范里新的实现方式

fetch是一个低层次的api  可以把它考虑成原生的xhr 所以使用起来并不是那么舒服 需要进行封装

fetch只对网络请求报错  对400 500都当作成功的请求  错误代码时并不会reject