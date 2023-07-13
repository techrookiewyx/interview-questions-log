### ES6+部分

1. 如何使用箭头函数定义一个匿名函数？
	- A：可以通过`const fn = ()={// 函数体 }`方式定义一个匿名函数
	- 解析：箭头函数是ES6中引入的一种新的函数的定义语法，它可以更简洁地定义函数，并且自动绑定了函数体内部的`this`值（箭头函数的this由其外城作用域决定）	
2. 如何使用模板字符串拼接字符串和变量？
	- A：模板字符串是ES6引入的一种新的字符串拼接语法。通过使用一对反引号\`包裹字符串，并在字符串中使用`${}`来插入变量，可以更方便地拼接字符串和变量，如下
		```js
		const name ='zhangsan';
		const message =`Hello, ${name}!`;
		```
3. 如何使用解构赋值从对象中提取属性值？
	- A：解构赋值是ES6引入的一种新语法，可以用于将数组或对象中提取元素和属性并赋值给变量。通过使用一对花括号`{}`来指定要提取的内容（属性名），来从对象中提取对应的属性值
		```js
		const person = { name:'tom', age:18 }
		const {name,age} = person;
4. 使用结构赋值，实现两个变量的值的交换
	- A：
	
		```js
		let a = 1;
		let b = 2;
		[a,b] = [b,a];
		```
	
5. 请解释一下ES6中的模块化
	- A：ES6中引入了模块化的概念，可以通过export和import关键字来导出和导入模块。模块化可以将代码分割成多个独立的文件，提高代码的可维护性和复用性。
6. 谈谈变量提升
	- A：当执行JS代码时，会生成执行环境，只要代码不是写在函数作用域中，就是在全局执行环境中，函数中的代码会产生函数执行环境。
		> 通常提升指的是说代码移动到了作用域顶部
		>
		> 但更准确的说是在生成执行环境时，创建阶段JS解释器会找出需要提升的变量和函数，给他们提前在内存中开辟好空间。所以在执行阶段我们可以直接提前使用
		>
		> 在提升的过程中，相同的函数会覆盖上⼀个函数， 并且函数优先于变量提升
		>
		> 变量提升是为了预留一些变量内存，以减少内存重新分配的次数，提升代码执行性能
7. let和const两个关键字与var之间有哪些不同？
	- A：其不同简要概括包括三点
		1. 不会发生变量提升现象。只有在声明变量那一行代码之后，才可以获取和使用该变量
			```js
			// let
			console.log(a)  // Cannot access 'b' before initialization
			let a = 10
			
			// const
			console.log(c)  // Cannot access 'c' before initialization
			const c = 10
			```
		2. 不覆盖全局变量（let和const声明的变量具有块级作用域）。其次与let又不同const用来声明一个常量，且在声明时必须初始化，而且一但声明就不能改变
			```js
			// let
			{ let b = 20 }
			console.log(b)  // Uncaught ReferenceError: b is not defined
			
			// const
			{ const c = 10 }
			console.log(c)  // Uncaught ReferenceError: c is not defined
			```
		3. 不允许重复声明（前提是在同一作用域中）
			```js
			// let 
			let a = 5;
			let a = 10; // Identifier 'b' has already been declared
			{
			   let a =10; // a =10;
			}
			
			// const
			const c = 10
			const c = 20; // Identifier 'c' has already been declared
			```
8. 解释下什么是暂时性死区？
	- A：通过let和const声明的变量会在进入块级作用域的时候被创建，但是在该变量没有赋值（声明）之前，在此阶段引用任何之后声明的变量都会报错，这种情况在语法上称为暂时性死区。
		暂时性死区是为了防止变量提升带来运行时出现的不可预知错误
9. ES5、ES6和ES2015有什么区别?
	- A：ES2015特指在2015年发布的	新一代JS语言标准。ES6泛指下一代JS语言标准，目前普遍认为ES2015默认等同ES6，ES5泛指上一代语言标准。ES2015可以理解为ES5和ES6的时间分界线。（新增箭头函数、解构复制、模块化、展开运算符、let和const等）
10. 什么是 IIFE (立即执行的函数)
	- A：立即执行函数是一个立即调用的匿名函数，它在创建后立即执行。立即执行函数会创建一个独立的作用域，通常用来避免污染全局命名空间（变量冲突）、页面加载完毕后的一些设置。
11. ES6中数组新增了哪些扩展?
	- A：
		1. 扩展运算符的应用，将一个数组转为用逗号分隔的参数序列
		2. 构造函数新增的方法`Array.from()`、`Array.of`
		3. 实例对象新增方法，如`find`、`includes`、`copyWithin`等
		4. 数组的空位（数组的某一个位置没有任何值），ES6 则是明确将空位转为`undefined`
		5. 排序稳定性，将`sort()`默认设置为稳定的排序算法
12. 介绍下 Set、Map的区别？
	- A：
		- Map：Map是一种叫做字典的数据结构，字典是一些元素的集合。每个元素有一个称作key 的域，不同元素的key 各不相同。Map中的键和值可以是任意类型的数据
		- Set：Set是一种叫做集合的数据结构，集合是是由一堆无序的、相关联的，且不重复的元素（内存结构）组成。它和数组功能类似，Set本质和Map一样只不过Set的key和value一样

		> 应用场景Set用于数据重组，Map用于数据储存
13. 下面Set结构，打印出的size值是多少？

	```js
	let s = newSet();
	s.add([1]);
	s.add([1]);
	console.log(s.size);
	```

	- A：打印结果为2，两个数组[1]并不是同一个值，它们分别定义了不同的数组（在内存中分别对应着不同的存储地址），因此并不是相同的值都能存储到Set结构中，所以size为2
14. 你是怎么理解ES6中 Promise的？
	- A：
		> Promise是异步的一种解决方法，解决了传统方案处理异步操作时出现的回调地狱问题。其优点如下：
		>
		> - 通过链式调用代替传统回调地狱减低了编码难度
		> - 增加代码可读性

		> Promise对象有三种状态分别是fulfilled（表示完成）、rejected（表示拒绝）、 pending（表示未完成），对象的状态不受外界影响，状态一但改变就不会再变。

		> Promise对象是一个构造函数，可以实例化一个对象，接收一个函数作为参数，该函数又有两个函数作为参数分别是`resolve`和`reject`，其作用分别是将Pomise对象的状态从“未完成”变为“成功”和从“未完成”变为“失败”。
		>
		> 通过Promise实例化的对象存在以下方法：
		>
		> - then（）：例状态发生改变时的回调函数，第一个参数是`resolve`状态的回调函数，第二个参数是`rejecte`状态的回调函数，该方法会返回一个Promise对象，所以Promise可以链式调用
		> - catch（）：用于指定发生错误时的回调函数，Promise 对象的错误具有“冒泡”性质，会一直向后传递，直到被捕获为止
		> - finally（）：用于指定不管 Promise 对象最后状态如何，都会执行的操作
		>
		> 除了上述的实例对象方法外，Promise还有一些静态方法：
		>
		> - Promise.all()：用于将多个 `Promise `实例，包装成一个新的 `Promise `实例，需要一个可迭代对象（数组）作为参数
		> - Promise.reject() / resolve() ：创建一个立即拒绝或完成状态的Promise对象（前提是参数不为Promise对象，若为Promise对象不做任何修改、原封不动地返回这个实例）
		> - Promise.race()：返回多个promise中执行最快的，它的参数需要传递一个可迭代对象（数组），不考虑完成或拒绝
		> - Promise.any()：返回多个promise中执行最快的完成的promise，若输入 Promise 都被拒绝时则返回错误
15. 下面的输出结果是多少
	```js
	const promise = new Promise((resolve, reject) => {
	    console.log(1);
	    resolve();
	    console.log(2);
	})
	
	
	promise.then(() => {
	    console.log(3);
	})
	
	
	console.log(4);
	
	```
	- A：Promise 新建后立即执行，所以会先输出 1、2，而 Promise.then()内部的代码在当次事件循环的结尾立刻执行 ，所以会继续输出4，最后输出3
16. setTimeout、Promise、Async/Await 的区别
	- A：在JS事件循环中任务队列分为宏任务队列和微任务队列
	
		> 其中setTimeout的回调函数放到宏任务队列里，等到执行栈清空以后执行
		>
		> promise.then里的回调函数会放到相应宏任务的微任务队列里，等宏任务里面的同步代码执行完再执行
		>
		> async函数表示函数里面可能会有异步方法，await后面跟一个表达式。async方法执行时，遇到await会立即执行表达式，然后把表达式后面的代码放到微任务队列里，让出执行栈让同步代码先执行
17. ES6中函数新增了哪些扩展?
	- A：
		- 对函数参数的扩展，ES6中允许为函数参数设置默认值，当参数是对象时可以进行解构。
		- 函数的length和name属性，`length`将返回不是指定默认值的参数个数，name属性返回该函数的函数名
	
			```js
			//如果设置了默认值的参数不是尾参数，那么length属性也不再计入后面的参数了
			(function (a = 0, b, c) {}).length // 0
			(function (a, b = 1, c) {}).length // 1
			```
		- 作用域：当为函数设置默认参数时，函数进行声明初始化时，参数会形成一个单独的作用域
	
			```js
			let x = 1;
			function f(y = x) { 
			  // 等同于 let y = x  
			  let x = 2; 
			  console.log(y);
			}
			f() // 1
			```
		- 严格模式，只要函数参数使用了默认值、解构赋值、或者扩展运算符，那么函数内部就不能显式设定为严格模式，否则会报错、
		- 箭头函数
18. 对 rest 参数的理解
	- A：通常用于指定函数形参上的可变参数，可以使函数接收任意数量的实参，并把多余的参数序列整合到一个数组中
		```js
		function mutiple(...args) {
		  let result = 1;
		  //遍历参数
		  for (var val of args) {
		    result *= val;
		  }
		  return result;
		}
		mutiple(1, 2, 3, 4) // 24
		
		//接收多余实参
		function fn(a,b,...args){
		   console.log(arg);  //输出 [3,4]
		}
		fn(1,2,3,4);
		```

		rest经常用于获取函数的多余参数，或者像处理函数参数个数不确定的情况
19. Promise 中reject 和 catch 处理上有什么区别
	- A：reject 是用来抛出异常，catch 是用来捕获和处理异常，reject 是 Promise 的方法，而 catch 是 Promise 实例的方法，reject的内容，一定会进入then中的第二个回调，如果then中没有写第二个回调，会直接进入catch而不会进入then的第二个回调
20. const创建对象的属性可以修改吗？
	- A：const所保证的是声明的变量指向的内存地址中的数据保持不变，对于基本数据类型来说内存地址中存储的就是值本身，而对于引用数据类型来说（主要是数组和对象），内存地址中保存的是一个指针（地址），const只能保证这个地址不发生变化。	