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
4. 使用解构赋值，实现两个变量的值的交换
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
		1. 扩展运算符的应用，将一个数组转为用逗号分隔的参数序列、合并数组、浅复制
		2. 构造函数新增的方法`Array.from()`、`Array.of`
		3. 实例对象新增方法，如`find`、`includes`、`copyWithin`、`fill`等
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
		> - then（）：当状态发生改变时的回调函数，第一个参数是`resolve`状态的回调函数，第二个参数是`rejecte`状态的回调函数，该方法会返回一个Promise对象，所以Promise可以链式调用
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
16. 说一下asyn和awit
	- A：
		- async：async是一个加在函数前的修饰符，被async定义的函数会默认返回一个Promise对象resolve的值。因此对async函数可以直接then，返回值就是then方法传入的函数
		- await：await 也是一个修饰符，只能在async定义的函数内使用。await修饰的如果是Promise对象可以获取Promise中返回的内容，且取到值后语句才会往下执行。如果不是Promise对象把其当做await表达式的结果。
17. setTimeout、Promise、Async/Await 的区别
	- A：在JS事件循环中任务队列分为宏任务队列和微任务队列
	
		> 其中setTimeout的回调函数放到宏任务队列里，等到执行栈清空以后执行
		>
		> promise.then里的回调函数会放到相应宏任务的微任务队列里，等宏任务里面的同步代码执行完再执行
		>
		> async函数表示函数里面可能会有异步方法，await后面跟一个表达式。async方法执行时，遇到await会立即执行表达式，然后把表达式后面的代码放到微任务队列里，让出执行栈让同步代码先执行
18. ES6中针对函数新增了哪些扩展?
	- A：
		- 对函数参数的扩展，ES6中允许为函数参数设置默认值，当参数是对象时可以进行解构。
		
		- 函数的length和name属性，`length`将返回不是指定默认值的参数个数，name属性返回该函数的函数名，如果设置了默认值的参数不是尾参数，那么length属性也不再计入后面的参数了
		
			```js
			(function (a = 0, b, c) {}).length // 0
			(function (a, b = 1, c) {}).length // 1
			```
			
		- 作用域：当为函数设置默认参数，函数进行声明初始化时，参数会形成一个单独的作用域
		
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
19. 对 rest 参数的理解
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
		
		// rest参数之后不能再有其他参数，否则会报错
		function f(a, ...b, c) {
		  // ...
		}
		```
		
		rest经常用于获取函数的多余参数，或者像处理函数参数个数不确定的情况
20. Promise 中reject 和 catch 处理上有什么区别
	- A：reject 是用来抛出异常，catch 是用来捕获和处理异常，reject 是 Promise 的方法，而 catch 是 Promise 实例的方法，reject的内容，一定会进入then中的第二个回调，如果then中没有写第二个回调，会直接进入catch而不会进入then的第二个回调
21. const创建对象的属性可以修改吗？
	- A：const所保证的是声明的变量指向的内存地址中的数据保持不变，对于基本数据类型来说内存地址中存储的就是值本身，而对于引用数据类型来说（主要是数组和对象），内存地址中保存的是一个指针（地址），const只能保证这个地址不发生变化。	
22. for in和for of 的区别和原理？
	- A：
		- for in：返回数据结构中的键名，遍历对象返回的是对象的key值，遍历数组返回的是数组的下标。还会遍历原型上的值和手动添加的值，所以 for in 适合遍历对象。
		- for of：for of 循环获取一对键值中的键值。一个数据结构只要部署了Symbol.iterator属性，就被视为具有iterator接口，可以使用for of。for of不同于forEach，for of是可以break，continue，return配合使用，for of 循环可以随时退出循环，总的说for of用于遍历可迭代对象。
23. 使用箭头函数应注意什么？
	- A：
		1. 用了箭头函数，this就不是指向window，而是父级（指向是可变的）
		2. 在箭头函数中不能够使用arguments对象
		3. 不能用作构造函数，这就是说不能够使用new命令，否则会抛出一个错误
		4. 不可以使用yield命令，因此箭头函数不能用作 Generator 函数
24. 扩展运算符的作用及使用场景
	- A：

		- 对象中使用：用于取出参数对象中的所有可遍历属性，拷贝到当前对象之中

			```js
			let bar = { a: 1, b: 2 };
			let baz = { ...bar }; // { a: 1, b: 2 }
			
			//若有重名的属性，放在扩展运算符后面，则扩展运算符内部的同名属性会被覆盖掉
			let bar = {a: 1, b: 2};
			let baz = {...bar, ...{a:2, b: 4}};  // {a: 2, b: 4}
			```

		- 数组中使用：可以将一个数组转为用逗号分隔的参数序列，且每次只能展开一层数组

			```js
			console.log(...[1, 2, 3])  // 1 2 3
			console.log(...[1, [2, 3, 4], 5])  // 1 [2, 3, 4] 5
			
			//对数组进行浅复制
			const arr1 = [1, 2];
			const arr2 = [...arr1];
			//合并数组
			const arr1 = ['2', '3'];
			const arr2 = ['1', ...arr1, '4', '5'];  // ["1", "2", "3", "4", "5"]
			
			//使用Math函数获取数组中特定的值
			const numbers = [9, 4, 7, 1];
			Math.min(...numbers); // 1
			Math.max(...numbers); // 9
			```
25. 箭头函数与普通函数的区别？
	- A：
		1. 箭头函数比普通函数更加简洁，当只有一个参数，可以省去参数的括号，当函数体的返回值只有一句，可以省略大括号和return。
		2. 箭头函数没有自己的this
		3. 箭头函数继承来的this指向永远不会改变，无法通过bind、call方法来改变箭头函数的this
		4. 箭头函数不能作为构造函数使用，因为没有自己的this
		5. 箭头函数没有自己的arguments，以及prototype
26. babel是什么，有什么作用?
	- A：babel是一个 ES6 转码器，可以将 ES6 代码转为 ES5 代码，它可以将使用了最新语法和特性的代码转换为可以在旧版本浏览器或其他环境中运行的代码。

		> 主要作用有以下几个方法：
		>
		> 1. 语法转换
		> 2. Polyfill填充：Babel可以根据目标环境的不同，自动添加缺失的JavaScript特性和API的Polyfill，以保证代码在不同环境中的兼容性
		> 3. 源码转换：Babel可以将源码中使用的其他语言（如JSX、TypeScript等）转换为纯JavaScript代码
		> 4. 插件扩展：Babel提供了丰富的插件系统，可以根据需要选择和配置不同的插件
27. ES6怎么写 class，为什么会出现 class 这种东西?
	- A：ES6 新添加的 class 只是为了补充 js 中缺少的一些面向对象语言的特性，但本质上来说它只是一种语法糖，不是一个新的东西，其背后还是原型继承的思想。通过加入 class 可以有利于我们更好的组织代码。在 class 中添加的方法，其实是添加在类的原型上的。
	
		```js
		class Point { 
		  constructor(x,y) { 
		      //构造方法
		       this.x = x; //this关键字代表实例对象
		       this.y = y; 
		  } toString() {
		       return '(' + this.x + ',' + this.y + ')'; 
		  }
		}
		```
28. .call和.apply是干什么用的，有什么区别？
	- A：他们都是函数的方法可以用来调用函数，第一个参数可以用于绑定函数的this指向（箭头函数除外），同时也可以给定其他参数，这些其他参数对应函数的实参。主要可以使用他们来给不同的对象绑定相同的方法。

		> 区别：
		>
		> call使用逗号分隔多个参数，而apply在接收参数时需要以（xx，[a,b,c]）数组的方式接收多余参数
29. 说出下面代码执行结果
	```js
	const promise = new Promise((resolve,reject)=>{
	    console.log(1);
	    resolve();
	    console.log(2);
	    reject()
	})
	setTimeout(()=>{console.log(5)},0)
	promise.then(()=>{console.log(3)})
	.then(()=>{console.log(6)})
	.catch(()=>{console.log(7)})
	console.log(4)
	```
	- A：1,2,4,3,6,5
	- 解析：

		> 1. 首先new Promise时候打印1和2，因为new Promise时候会立即执行传入的方法
		> 2. 然后先将setTimeout的回调加入宏任务队列，再把promise.then放入到微任务队列
		> 3. 然后执行执行栈中的同步任务打印4
		> 4. 当执行栈中任务执行完毕接下来开始执行微任务队列中的任务，由于promise resolve，因为promise resolve之后状态不会再改变，因此不会执行到reject的回调，所以打印3和6微任务队列为空
		> 5. 再到宏任务队列中查找任务，找到setTimeout回调压入执行栈执行，打印5。
30. es6继承，子类会继承父类的静态成员吗？
	- A：会继承，除了私有属性，父类的所有属性和方法，都会被子类继承，其中包括静态方法。 
31. 说一说Symbol，以及注意点
	- A：Symbol是一种基本类型。Symbol 通过调用Symbol函数产生，它接收一个可选的名字参数，该函数返回的symbol是唯一的，可以用来定义对象的唯一属性名，也可以替换string避免不同的模块属性的冲突。

		> symbol特点以及注意点如下：
		>
		> 1. Symbol的值和谁都不相等是独一无二的值，且不能与其他类型进行运算。
		>
		> 2. Symbol不能用new关键字，symbol值不是对象，所以不能添加属性
		>
		> 3. Symbol值定义属性时，必须放在方括号内，不能用点运算符。
		>
		> 	```js
		> 	let name = Symbol()
		> 	let obj = {}
		> 	obj[name] = “Alice”
		> 	cosnole.log(obj[name])
		> 	```
		>
		> 4. Symbol 函数可以接受一个字符串作为参数，表示对 Symbol 实例的描述，主要是为了在控制台显示，或者转为字符串时，比较容易区分（无法转换为数值）
		>
		> 5. Symbol 作为属性名，该属性不会出现在 for...in、for...of 循环中，也不会被 Object.keys()、Object.getOwnPropertyNames()、JSON.stringify() 返回。
		>
		> 6. 可以通过Object.getOwnPropertySymbols方法，获取给定对象的所有自有Symbol作为属性名的数组
		>
		> 7. Symbol.for 接受一个字符串作为参数，然后搜索有没有以该参数作为名称的 Symbol 值。如果有，就返回这个 Symbol 值，否则就新建并返回一个以该字符串为名称的 Symbol 值。
32. Async/Await 如何通过同步的方式实现异步 
	- A：async await 用于把异步请求变为同步请求的方式,第一个请求的返回值作为后面一个请求的参数,其中每一个参数都是一个promise对象

		```js
		(async () => {
		    var a = await A();
		    var b = await B(a);
		    var c = await C(b);
		    var d = await D(c);
		})()
		```
33. ES6中的字符串方法startsWith()和endsWith()有什么用途？
	- A：startsWith()和endsWith()是ES6中新增的字符串方法，用于判断字符串是否以指定的字符开始或结束。它们返回布尔值，可以用于快速检查字符串的前缀或后缀。
34. 如何使用Set去重
	- A：

		```js
		let arr = [12,43,23,43,68,12];
		//这里也可以使用Array.from(new Set(arr))来将Set转回数组
		let item = [...new Set(arr)];
		console.log(item);//[12, 43, 23, 68]
		```
35. 将下面for循环改成for of形式
	```js
	let arr = [11,22,33,44,55];
	let sum = 0;
	for(let i=0;i<arr.length;i++){
	    sum += arr[i];
	}
	```
	- A：
		```js
		let arr = [11,22,33,44,55];
		let sum = 0;
		for(value of arr){
		    sum += value;
		}
		```
36. 举一些ES6对String字符串类型做的常用升级优化?
	- A：
		- ES6新增了模块字符串，用反斜杠(`)取代以往的字符串相加的形式，能保留所有空格和换行并且可以通过（$）加花括号来拼接变量，使得内容拼接看起来更加直观。
		- ES6在String原型上新增了includes()方法，用于取代传统的只能用indexOf查找包含字符的方法, 此外还新增了startsWith()，endsWith()，padStart()，padEnd()，repeat()等方法，可方便的操作字符串。
37. ES6中的数组方法reduce()和reduceRight()有什么区别？
	- A：reducer方法按升序对数组中的每个元素按序执行一个提供的 **reducer** 函数，回调函数仅对已分配值的数组索引进行调用，每一次运行 **reducer** 会将先前元素的计算结果作为参数传入，最后将其结果汇总为单个返回值。——也可以说对数组中的元素进行迭代并返回一个累积值。

		> reduceRight与reduce都可以同于对数组元素进行一个累积计算，唯一区别是reduce()从左到右计算，reduceRight()从右到左计算
		>
		> ```js
		> const numbers = [1, 2, 3, 4, 5];
		> const sum = numbers.reduce((accumulator, currentValue) => {return accumulator + currentValue;},0);
		> console.log(sum); // 输出：15
		> 
		> 
		> const numbers = [1, 2, 3, 4, 5];
		> const reversedString = numbers.reduceRight((accumulator, currentValue) => {
		>   return accumulator + currentValue;
		> }, "");
		> console.log(reversedString); // 输出："54321"
		> ```
38. 下面代码输入什么结果

	```js
	class Chameleon {
	  static colorChange(newColor) {
	    this.newColor = newColor
	    return this.newColor
	  }
	
	  constructor({ newColor = 'green' } = {}) {
	    this.newColor = newColor
	  }
	}
	
	const freddie = new Chameleon({ newColor: 'purple' })
	freddie.colorChange('orange')
	```

	- A：会报错，colorChange 是一个静态方法。静态方法被设计为只能被创建它们的构造器使用（也就是 Chameleon，也可以通过继承的方式让子类继承父类的静态方法），并且不能传递给实例。因为 freddie 是一个实例，静态方法不能被实例使用，因此抛出了TypeError 错误。
39. Object.keys()和Object.values()有什么作用
	- A：Object.keys()用于返回一个对象的所有可枚举属性的键数组，Object.values()用于返回一个对象的所有可枚举属性的值数组。

		```js
		const user = {
		  name: 'Alice',
		  age: 25,
		  email: 'alice@example.com'
		};
		
		const keys = Object.keys(user);
		console.log(keys); // 输出：['name', 'age', 'email']
		
		const values = Object.values(user);
		console.log(values); // 输出：['Alice', 25, 'alice@example.com']
		
		```
		
		使用场景：Object.keys()和Object.values()通常用于遍历对象的键和值，或者用于将对象的键或值转换为数组进行进一步处理。
40. ES6中的类继承是如何实现的？
	- A：ES6中的类继承使用extends关键字来实现，子类可以继承父类的属性和方法，并且可以添加自己的属性和方法。可以通过调用super()方法来调用父类的构造函数。
41. ES6中的Array方法some和every的作用是什么？

	- A：ES6中的Array方法some用于判断数组中是否存在满足条件的元素，只要有一个元素满足条件即返回true；every用于判断数组中所有元素是否都满足条件，只有所有元素都满足条件才返回true。

		```js
		const numbers = [1, 2, 3, 4, 5];
		// 使用some判断是否存在大于3的元素
		const hasGreaterThan3 = numbers.some(num => num > 3);
		console.log(hasGreaterThan3); // 输出：true
		// 使用every判断是否所有元素都大于0
		const allGreaterThan0 = numbers.every(num => num > 0);
		console.log(allGreaterThan0); // 输出：true
		```
42. 下面代码会输出什么？
	```js
	const shape = {
	  radius: 10,
	  diameter() {
	    return this.radius * 2
	  },
	  perimeter: () => 2 * Math.PI * this.radius
	}
	shape.diameter()
	shape.perimeter()
	```

	- A：20和NaN
	- 解析：diameter()是一个常规函数，它的this指向最后调用它的对象（在该案例中是shape，shape有redius属性所以输出 10*2 ）。而perimeter()是一个箭头函数，箭头函数的this指向的是它当前周围作用域（简单来说是包含箭头函数的常规函数，如果没有常规函数的话就是全局对象，而window中没有radius所以为undefined）
43. 简单介绍下ES6中的Iterator迭代器

	- A：`Iterator` 是一种接口（或称为迭代器对象，本质就是一个指针对象），Iterator为为不同的数据结构提供统一的数据访问机制，比如for of就是依靠Iterator迭代器来实现的。

		> Iterator对象具有一个`next`方法，每次调用 `next` 方法都会使其指向下一个成员并且会返回一个对象，包含两个属性，`value`（当前成员的值） 和 `done`（布尔值表示遍历是否结束）
		>
		> ```js
		> //模拟next方法返回值
		> function makeIterator(array) {
		>   var nextIndex = 0;
		>   return {
		>     next: function() {
		>       return nextIndex < array.length ?
		>         {value: array[nextIndex++], done: false} :
		>         {value: undefined, done: true}
		>     }
		>   }
		> }
		> ```
		>
		> 默认的 Iterator 接口部署在数据结构的`Symbol.iterator`属性（本身就是一个函数），只要对象中部署了`Symbol.iterator`属性那么这个对象就称为可迭代对象（就可以使用for-of来遍历）
		>
		> 原生具备 Iterator 接口的对象有：Array、String、Map、Set、函数的 arguments 对象、NodeList

		在解构赋值、扩展运算符、yield*、以及一些以数组为参数的场合都会默认调用 Iterator 接口
