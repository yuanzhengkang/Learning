call() 和apply()的第一个参数相同，就是指定的对象。这个对象就是该函数的执行上下文。

call()和apply()的区别就在于，两者之间的参数。

call()在第一个参数之后的  后续所有参数就是传入该函数的值。apply() 只有两个参数，第一个是对象，第二个是数组，这个数组就是该函数的参数。

例1：
var obj = {};
 
function foo(a, b, c) {
  console.log(b);
}
 
foo.call(obj, 1, 2, 3)   //打印结果： 2;
　　

例2：
var obj = {};
 
function foo(a, b, c) {
  console.log(b);
}
 
foo.apply(obj, [1, 2, 3])   打印结果： 2;

bind() 方法和前两者不同在于： bind() 方法会返回执行上下文被改变的函数而不会立即执行，而前两者是直接执行该函数。他的参数和call()相同。