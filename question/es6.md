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
	
4. 请解释一下ES6中的模块化
	- A：ES6中引入了模块化的概念，可以通过export和import关键字来导出和导入模块。模块化可以将代码分割成多个独立的文件，提高代码的可维护性和复用性。
5. let和const两个关键字与var之间有哪些不同？
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
6. 解释下什么是暂时性死区？
	- A：通过let和const声明的变量会在进入块级作用域的时候被创建，但是在该变量没有赋值（声明）之前，在此阶段引用任何之后声明的变量都会报错，这种情况在语法上称为暂时性死区。
		暂时性死区是为了防止变量提升带来运行时出现的不可预知错误