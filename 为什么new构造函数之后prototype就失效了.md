对象寻找原型链是通过__proto__属性来寻找的，每一个构造函数在声明之后就会在内存中同步开辟一个空间保存一个对象
构造函数中会有一个prototype指向这个对象 而这个对象中会有一个constructor属性指向构造函数
如果要转换实例构造函数的prototype指向可以通过new构造函数的prototype.constructor改变其this指向

function A() {
				this.name = 'abc';
			}
			A.prototype.showName = function() {
				console.log(this.name)
			}

			function B() {
				//this指向是new出来的B   B.name = 'abc';
				A.call(this);
			}
			for (var i in A.prototype) {
				B.prototype[i] = A.prototype[i]
			}
			B.prototype.constructor = A		//此步骤就是改变原型指向
			B.prototype.fn = function() {
				console.log('123')
			}
			var objB = new B();
			var objA = new A();
			// alert(B.name)
			objB.showName()	//abc
			console.log(objA.prototype)	//undefined
			console.log(objB.prototype) //undefined