## React部分

1. 如何在React中处理表单输入？
	- A：使用React的受控组件来处理表单输入。通过将表单元素的值绑定到组件的状态变量上，并在`onChange`事件中更新状态，可以实现实时更新表单输入的效果。
	- 解析：将表单元素的值绑定到组件的状态来实现受控组件。通过`<input>`元素上设置`value`属性为组件的状态，在`onChange`事件中更新状态，以达到实时更新表单输入的效果
2. 如何在React中进行组件间通信？
	- A：通过state和props来实现react组件间的通信。通过将数据作为props传递给子组件，或者通过改变state来触发组件的重新渲染，以达到组件间通信
3. 如何在React中处理组件的生命周期？
	- A：可以使用React的生命周期方法来处理组件的生命周期，如`componentDidMount`方法会在组件挂载后调用，`componentWillUnmount`方法会在组件卸载前调用。
	- 解析：React组件的生命周期包括挂载、更新和卸载三个阶段。通过在组件中定义生命周期方法，可以在不同的阶段执行相应的操作
4. 请解释一下React中的虚拟DOM。
	- A：虚拟DOM是React中的一种概念，它是用JavaScript对象来表示真实DOM的一种抽象（React通过虚拟DOM将React元素和真实DOM进行映射）。在React中，当数据发生变化时，React会通过比较虚拟DOM和真实DOM的差异，然后只更新需要更新的部分，从而提高性能。
5. 请解释一下React中的状态（state）和属性（props）。
	- A：React中的状态是组件内部的数据，状态是可以改变的，当状态发生变化时，React会自动重新渲染组件。`react`具有单向数据流的特性，所以属性通常是从父组件传递给子组件的的数据，属性只能由父组件修改。
6. 说说对React的理解？有哪些特性？
	- A：React就是用来构建用户界面的JavaScript库，循序组件设计模式、声明式编程和函数式编程，使前端应用程序更高效，使用虚拟DOM来操作DOM，遵循高阶组件到低阶组件的单向流数据。
		React具有很多特性，如`JSX语法`、`单向数据绑定`、`虚拟DOM`、`声明式编程`、`组件化开发`
		
		> 优势：
		>
		> 1. 高效灵活
		> 2. 声明式的设计，简单实用
		> 3. 组件式开发，提高代码复用率
		> 4. 单向响应的数据流更安全，速度更快
7. 请描述你对纯函数的理解？
	- A：固定的输入，有固定的输出，且不包含任何副作用的函数称之为纯函数。纯函数不会更改函数调用前就存在的变量或对象。
8. React的严格模式有什么用处？
	- A：在React中严格模式仅在开发环境中生效，严格模式用 `<React.StrictMode>`标签来包裹想要检查的组件，严格模式会调用每个组件两次，可以用于帮助我们：
		- 识别不安全的生命周期
		- 使用过时的API时发出警告
		- 检测存在副作用的组件
		- 检测不安全的使用方式（如使用废弃的context API）
	
		综上严格模式可以帮只我们更早发现潜在问题。
9. React中的key有什么作用？
	- A：在React的列表渲染中每一个子元素都应该需要一个唯一的key值（通常我们使用id来作为key）， key 会告诉 React，每个组件（元素）对应着数组（列表）里的哪一项，用来标识唯一元素 
		> 元素`key`属性的作用是用于判断元素是新创建的还是被移动的元素（当设置key属性后，元素再进行比较时，就不会按照顺序比较，而是按照相同key属性值进行比较），从而减少不必要的修改
		>
		> 如果只是文本内容改变了，不写`key`反而性能和效率更高，但如果涉及到节点的删除和新增，则key可以增加性能的开销	
10. 说说对受控组件和非受控组件的理解？应用场景？
	- A：对于每个独特的状态，都应该存在且只存在于一个指定的组件中作为 state，这一原则成为可信单一数据源
		- 受控组件简单来说就是受我们控制的组件，当组件中的重要信息是由 props 而不是其自身状态驱动时，就可以认为该组件是受控组件，其行为完全由父组件指定。以一个输入框为例，若想要输入框中内容随着用户输入而变化，通常需要一个初始状态和状态更新函数才能实现受控输入框
	
		- 非受控组件，通常把包含不受状态控制的组件称为非受控组件，简单来讲，就是不受我们控制的组件。一般情况是在初始化的时候接受外部数据，然后自己在内部存储其自身状态。当需要时，可以使用`ref` 查询 `DOM `并查找其当前值
	
		- 应用场景如下
	
			|         特征         | 非受控 | 受控 |
			| :------------------: | :----: | :--: |
			| 一次性取值（提交时） |   √    |  √   |
			|      提交时验证      |   √    |  √   |
			|     即时现场验证     |   ×    |  √   |
			| 有条件地禁用提交按钮 |   ×    |  √   |
			|     强制输入格式     |   ×    |  √   |
			|  一个数据的多个输入  |   ×    |  √   |
			|       动态输入       |   ×    |  √   |
11. React构建组件的方式有哪些？区别？
	- A：组件就是把图形、非图形的各种逻辑均抽象为一个统一的概念来实现开发的模式（组件本质是一段可以使用标签进行扩展 的JavaScript函数）。在React中可以将页面内容拆分成一个一个组件，一个类、一个函数都可以视为一个组件，组件是构建用户界面的基础。组件的构建主要分成了三种：
	
		- 函数式创建：在Hooks出来之前，函数式组件可以视为无状态组件，只负责根据传入的props来展示视图，不涉及对state状态的操作。函数式创建的组件，最终会通过babel转化成React.createElement的形式

			```jsx
			//可以通过如下方式构建函数组件
			function HelloComponent(props) {
			  return <div>Hello {props.name}</div>
			}
			```
	
		- 通过 React.createClass方法创建：是react刚开始推荐的创建组件的方式，这是一种及其老的方式，目前基本不会使用了。
	
		  ```jsx
		  const MyComponent = React.createClass({
		    // 通过proTypes对象和getDefaultProps()方法来设置和获取props
		    propTypes: {
		      name: React.PropTypes.string
		    }
		    // 通过getInitialState()方法返回一个包含初始值的对象
		    getInitialState(){ 
		          return {sayHello: 'Hello Srtian'}
		     }
		     render() {
		      return <p></p>
		    }
		  })
		  ```
		
		- 继承 React.Component创建：这种形式进行创建有状态的组件，在类创建的方式中通过`this.state`进行访问，当调用`this.setState`修改组件的状态时，组件会再次会调用render()方法进行重新渲染，下面是一个简单案例：
		
			```jsx
			class Timer extends React.Component {
			  constructor(props) {
			    super(props);
			    this.state = { count: 0 };
			  }
			  clickHandle= () => {
			    this.setState(state => ({
			      count: state.count + 1
			    }));
			  }
			
			  render() {
			    return (
			      <button onClick={this.clickHandle}>
			        Count: {this.state.count}
			      </button>
			    );
			  }
			}
			```
12. 说说对React中类组件和函数组件的理解？有什么区别？
	- A：
		- 类组件：就是使用ES6中类的形式去编写组件，该类必须继承`React.Component`，在组件中必须实现`render()`方法，在return中返回React对象，通过`this.props`访问父组件传递的参数
		- 函数组件：通过函数形式去实现React组件，函数参数作为props接收父组件传递的参数
		区别分为如下几个方面：
	
		> （1）编写形式
		>
		> （2）状态管理：在hooks出来之前，函数组件是无状态组件，不能保存组件的状态
		>
		> （3）生命周期：在函数组件中，并不存在生命周期，因为声明周期的方法继承`React.Component`，但函数组件中可以使用`useEffet`来达到替代生命周期的作用
		>
		> （4）调用方式：函数组件直接调用即可，类组件需要进行实例化，然后调用实例对象的render方法
		>
		> （5）获取渲染的值：类组件中this使用过多
13. 说说react中引入css的方式有哪几种？区别？
	- A：方式有如下几种

		- 在组件内通过style属性设置

			> 优点：内联样式不会有冲突、可以动态设置样式
			>
			> 缺点：大量样式造成代码混乱、某些样式无法编写

		- 组件中引入.css文件

			> 符合我们日常的编写习惯，但是作用域是全局的，样式之间会层叠和冲突

		- 组件中引入 .moudle.css文件

			> 优点：只针对当前模块生效，不会发生冲突
			>
			> 缺点：不方便动态修改样式，需要使用内联的方式进行样式的编写

		- CSS in JS 是一种模式，CSS由JS生成不用通过外部文件定义有第三方库提供（styled-components、emotion）

			> 满足大部分场景的应用，可以类似于预处理器一样样式嵌套、定义、修改状态
14. 说说React中JSX语法
	- A：JSX既不是字符串，也不是HTML，而是一种类似XML，用于描述用户界面的JavaScript扩展语法，可以用于创建React元素，它只是为React.createElement()提供语法糖（16.x版本），从而让在我们在 JavaScript中，使用类 HTML 模板的语法。JSX为视图和数据架起了一座沟通的桥梁，JSX最终会被编译成普通的JavaScript对象，所以能够直接使用JavaScript语法，因此我们可以在JS中编写JSX。
	
		> 在JSX的任意位置都能插入变量，但必须用花括号包裹住才能有效。
		>
		> JSX中会自动将数组中元素在页面中显示
		>
		> 可以直接为标签设置属性
	
		编写JSX需要遵循以下规则：
		
		- 必须用一个跟元素包裹其它元素或文本（因为JSX在底层被转化为了JS对象，一个函数中不能返回多个对象）
		- 所有的元素还必须得闭合
15. 说说 React中的setState执行机制
	- A：
		> 一个组件显示什么内容是由数据状态和外部参数所决定，而数据状态就是`state`，若想更新组件内部的数据，则需要通过setState来修改state的值。如果直接修改state的值，会发现页面不会发生任何变化（此时state已经被我们修改了），因为React中必须通过`setState`方法来告知`react`组件`state`已经发生了改变。setState的第一个参数可以是一个对象或函数，而第二个参数是一个回调函数，用于可以实时的获取到更新之后的数据
	
		> 在使用setState更新数据时，setState的更新分为同步更新和异步更新
		>
		> - 在组件生命周期或React合成事件中，setState是异步
		> - 在setTimeout或者原生dom事件中，setState是同步
16. 说说 Real DOM和 Virtual DOM 的区别？优缺点？
	- A：
		区别如下：
	
		> - 虚拟DOM不会进行排版与重绘操作，而真实DOM会频繁重排与重绘
		> - 虚拟DOM的总损耗是“虚拟DOM增删改+真实DOM差异增删改+排版与重绘”，真实DOM的总损耗是“真实DOM完全增删改+排版与重绘”
		>
		> 当你在一次操作时，若需要更新10个`DOM`节点，浏览器收到第一个更新`DOM`请求后，并不知道后续还有9次更新操作，最终执行10次流程
		>
		> 而虚拟节点不会立即操作DOM，而是将这10次更新的`diff`内容保存到本地的一个`js`对象中，最终将这个`js`对象一次性`attach`到`DOM`树上，避免大量的无谓计算
	
		优缺点：
	
		> 真实DOM：
		>
		> - 优点：易用，针对低频次、低复杂度的DOM操作时性能较好
		> - 缺点：
		> 	1. 效率低，解析速度慢，内存占用量过高
		> 	2. 性能差：频繁操作真实DOM，易于导致重绘与回流
		>
		> 虚拟DOM：
		>
		> - 优点：
		> 	1. 简单方便
		> 	2. 提高性能：在复杂场景下，能够有效避免对真实DOM频繁操作，减少多次引起重绘与回流，提高性能
		> - 缺点：首次渲染速度慢、无法针对性的作出优化
	
		解析：
	
		- Real DOM：真实DOM，意思为文档对象模型，是一个结构化文本的抽象，在页面渲染出的每一个结点都是一个真实`DOM`结构
		- Virtual DOM：本质上是以 `JavaScript` 对象形式存在的对 `DOM` 的描述，创建虚拟`DOM`目的就是为了更好将虚拟的节点渲染到页面视图中，与真实DOM进行映射。React中的虚拟DOM就是通过将JSX转化为JS对象来实现的
17. React中组件之间的通信方式？
	- A：根据传送者和接受者可以将通信方式分为以下几种：
		> - 父组件向子组件传递：React的数据流动是单向的，父组件通过 props 向子组件传递需要的信息
		> - 子组件向父组件传递：本质也是通过props实现，需要父组件传递一个函数作为props，通过回调函数将信息发送给父组件
		> - 祖先组件向后代组件传递：使用context，context相当于一个大容器，我们可以把要通信的内容放在这个容器中，对于跨越多层的全局数据可以使用context实现
		> - 非嵌套关系组件传递：将数据进行一个全局资源管理，从而实现通信，例如`redux`。若是兄弟节点，可以找到其共同父组件
18. 说说你对声明式编程的理解？
	- A：声明式编程就是以结果为导向的编程，区别于命令式不用我们一步一步的告诉计算机要做什么，最后产生什么结果，声明式只需告诉计算机要什么结果，不关心过程。
19. react的状态提升是什么？使用场景有哪些？
	- A：
		- 概念：当多个组件需要公用一些状态时，把共有的状态提取到父组件中并通过props将数据或信息传递到子组件，这就是状态提升，这样统一了数据来源，使逻辑更加清晰。
		- 使用场景：子组件的数据相互耦合，相互依赖，可能还存在相互修改的情况下使用。
20. 说说React的事件机制？
	- A：
		- 在React中的事件机制被称之为合成事件（循序W3C规范来定义合成事件，兼容所有浏览器），合成事件是 `React `模拟原生 `DOM `事件所有能力的一个事件对象，基于浏览器的事件机制自身实现了一套事件机制，包括事件注册、事件的合成、事件冒泡、事件派发等，如：
			```jsx
			//e.nativeEvent可以获取原生DOM事件，e代表事件对象
			const handleClick = (e) => console.log(e.nativeEvent);;
			const button = <button onClick={handleClick}>按钮</button>
			```

			> 虽然onClick看似绑定到了DOM上但实际并不会把事件代理函数直接绑定到真实的节点上，而是把所有的事件绑定到结构的最外层，使用一个统一的事件去监听。
			>
			> 这个事件监听器上维持了一个映射来保存所有组件内部的事件监听和处理函数。当组件挂载或卸载时，只是在这个统一的事件监听器上插入或删除一些对象
			>
			> 当事件发生时，首先被这个统一的事件监听器处理，然后在映射里找到真正的事件处理函数并调用（React 通过队列的形式，从触发的组件向父组件回溯，然后调用他们 JSX 中定义的 callback）。这样做简化了事件处理和回收机制，效率也有很大提升

		- 关于执行顺序：React 所有事件都挂载在 document 对象上，而不是 React 组件对应的 DOM(减少内存开销就是因为所有的事件都绑定在 document 上，其他节点没有绑定事件)

			1. 当真实 DOM 元素触发事件，会冒泡到 document 对象后，再处理 React 事件
			2. 所以会先执行原生事件，然后处理 React 事件
			3. 最后真正执行 document 上挂载的事件
21. 为什么说React中的props是只读的？
	- A：这样保证react的单向数据流的设计模式，使状态更可预测。如果允许组件修改，那么一个父组件将状态传递给好几个子组件，这几个子组件随意修改，就完全不可预测，不知道在什么地方修改了状态。为了保证组件像纯函数一样没有响应的副作用，所以我们必须像纯函数一样保护 props 不被修改。
22. React事件绑定的方式有哪些？区别？
	- A：在react中，事件名都是用小驼峰格式进行书写，且事件的绑定使用`{}`包裹，其绑定方法如下（类组件中）：

		- render方法中使用bind，在其中给某个组件/元素一个`onClick`属性，它并不会自动绑定其`this`到当前组件，可以通过在事件函数后使用`.bind(this)`将`this`绑定到当前组件中

			```jsx
			class App extends React.Component{
			    handleClick() {
			    console.log('this > ', this);
			  }
			  render() {
			    return (
			      <div onClick={this.handleClick.bind(this)}>test</div>
			    )
			  }
			}
			```

			该绑定方式在组件每次render渲染时，都会重新进行this的绑定，影响性能

		- render方法中使用箭头函数，通过ES6的上下文来将`this`的指向绑定给当前组件，同样每一次render的时候都会生成新的方法，影响性能

			```jsx
			class App extends React.Component{
			    handleClick() {
			    console.log('this > ', this);
			  }
			  render() {
			    return (
			      <div onClick={e=>this.handleClick(e)}>test</div>
			    )
			  }
			}
			```

		- constructor中bind，可以避免在`render`操作中重复绑定

			```jsx
			class App extends React.Component{
			   constructor(props) {
			    super(props);
			    this.handleClick = this.handleClick.bind(this);
			  }
			   handleClick() {
			    console.log('this > ', this);
			  }
			  render() {
			    return (
			      <div onClick={this.handleClick}>test</div>
			    )
			  }
			}
			```

		- 定义阶段使用箭头函数绑定，同样可以避免重复绑定，实现也非常的简单

			```jsx
			class App extends React.Component{
			   handleClick= () => {
			    console.log('this > ', this);
			  }
			  render() {
			    return (
			      <div onClick={this.handleClick}>test</div>
			    )
			  }
			}
			```

		区别：

		> 编写方面：方式一、方式二写法简单，方式三的编写过于冗杂
		>
		> 
		>
		> 性能方面：方式一和方式二在每次组件render的时候都会生成新的方法，性能问题欠缺。若该函数作为属性值传给子组件的时候，都会导致额外的渲染。而方式三、方式四只会生成一个方法实例，四是最优解
23. 描述下在react中无状态组件和有状态组件的区别是什么？
	- A：状态即是state，在hooks出现之前函数组件都是无状态组件
		- 无状态组件：无状态组件主要用于内容展示，接收来自父组件props传递过来的数据，使用props来展示父组件传递的内容。无状态组件应该保持模板的纯粹性，以便于组件复用。
		- 状态组件：状态组件主要用来定义交互逻辑和业务数据，有自己的state，需要处理副作用等反馈到state上。
24. 说一下setState原理
	- A：setState操作并不保证是同步的，也可以认为是异步的，React在setState之后，会对state进行diff，判断是否有改变，然后去对比差异决定是否要更新界面。 如果这一系列过程立刻发生在每一个setState之后，就可能会有性能问题.。在短时间内频繁setState，React会将state翻遍压入栈中，在合适的时机批量更新state和视图，达到提高性能的效果。
25. react中遍历时为什么不用索引作为唯一的key值？
	- A：key值的目的在Diff DOM的时候让React可以根据更新前后的唯一key值快速的对树进行比较，从而得以正确地更新 DOM 树，如在进行中间插入或者最顶上插入时，算法会很明显得知道这是一个插入动作，然后让后续的节点往后移位，如果是以索引index作为key值，那么在进入上述的操作后，插入后面的元素key值完全变了，算法不能准确的定位到树中node的位置，只能从插入的位置起，后续的全部重新生成，影响性能
26. 在React中如何引入图片？哪种方式更好？
	- A：
		- 通过import将图片当做模块导入

			```jsx
			import Img from "./images/1.png"
			function App(){
			  return(
			    <div><img src={Img} alt='Logo'/></div>
			  )
			}
			```

		- 通过require直接获取图片

			```jsx
			function App(){
			  return(
			    <div><img src={require('./images/1.png')} alt='Logo'/></div>
			  )
			}
			```

		两种方法显示效果相同没有本质却别，`import`方式更符合ES6的模块化规范，可以直接在代码中使用引入的图片，而`require`方式更符合CommonJS的模块化规范，需要使用`require()`函数引入图片
27. 说说对高阶组件的理解？应用场景? 
	- A：高阶函数（Higher-order function），至少满足`接受一个或多个函数作为输入`、或`输出一个函数`的函数。在React中，高阶组件即接受一个或多个组件作为参数并且返回一个组件，本质也就是一个函数，并不是一个组件。

		```jsx
		const EnhancedComponent = highOrderComponent(WrappedComponent); 
		//高阶函数的上述实现方法，本质上是一个装饰者设计模式
		```

		- 最基本的高阶组件模版如下：

			```jsx
			import React, { Component } from 'react';
			
			export default (WrappedComponent)=>{
			  return class EnhancedComponent extends Component {
			    // do something
			    render() {
			      return <WrappedComponent />;
			    }
			  }
			}
			```

			高阶组件的主要功能是封装并分离组件的通用逻辑，让通用逻辑在组件间更好地被复用

			> 在使用高阶组件的同时，一般遵循一些约定：
			>
			> 1. props 保持一致
			> 2. 你不能在函数式（无状态）组件上使用 ref 属性，因为它没有实例
			> 3. 不要以任何方式改变原始组件 WrappedComponent
			> 4. 透传不相关 props 属性给被包裹的组件 WrappedComponent
			> 5. 不要再 render() 方法中使用高阶组件
			> 6. 使用 compose 组合高阶组件
			> 7. 包装显示名字以便于调试

		高阶组件能够提高代码的复用性和灵活性，常常用于与核心业务无关但又在多个模块使用的功能，如权限控制、日志记录、数据校验、统计上报等
28. 说说对React Hooks的理解？解决了什么问题？
	- A：Hook 是 React 16.8 的新增特性。它可以让你在不编写 class的情况下使用state以及其他的 React 特性。hook的引入是为了解决一些类组件的问题：

		> 1. 复杂且不容易理解的“this”
		> 2. 难以重用和共享组件中的与状态相关的逻辑
		> 3. 逻辑复杂的组件难以开发与维护，每个生命周期函数中可能会包含着各种互不相关的逻辑在里面

		常用HOOK有：

		> - useState：能够解决类组件所有自定义变量只能存储在this.state的问题
		> - useEffeact：能够在函数组件中进行一些带有副作用的操作，解决类组件某些执行代码被分散在不同的生命周期函数中的问题
		> - useReducer、useContext、useCallback等

		HOOK扩展了函数组件的功能使函数组件拥有类组件的相似功能。可以通过自定义Hook，将数据状态逻辑从组件中抽离出去，这样同一个Hook可以被多个组件使用，解决组件数据状态逻辑并不能重用的问题。
29. 你了解React中的Fragment吗
	- A：

		> 我们常用的<\>\</>就是\<Fragment> 的简写语法，\<Fragment> 可以将其他元素组合起来，且不会在文档中添加额外节点（不会影响布局和样式）
		>
		> 当你在循环中渲染多个元素时可以使用\<Fragment>来为每一个元素分配key，也就是说\<Fragment> 可以设置key属性
30. 说一说state的批处理
	- A：我们先看一下如下案例：

		```jsx
		import { useState } from 'react';
		export default function Counter() {
		  const [number, setNumber] = useState(0);
		
		  return (
		    <>
		      <h1>{number}</h1>
		      <button onClick={() => {
		        setNumber(number + 1);
		        setNumber(number + 1);
		        setNumber(number + 1);
		      }}>+3</button>
		    </>
		  )
		}
		```

		你不是以为点击按钮后number的值会变为3，但最终number结果是1。因为state在一次渲染的事件处理函数中是不变的也就是说number一直是0，其次还有如下原因导致了这个结果

		React会等到事件处理函数中的所有代码都运行完毕再处理你的state更新（UI才会更新），这也就意味着你可以在一个事件处理函数中同时更新多个state而不会触发多次重新渲染，这就是批处理。
31. 什么是 Pure Components?
	- A：React.PureComponent与React.Component 完全相同，只是它为你处理了 shouldComponentUpdate() 方法。当属性或状态发生变化时，PureComponent 将对属性和状态进行**浅比较**。另一方面，一般的组件不会将当前的属性和状态与新的属性和状态进行比较。因此，在默认情况下，每当调用shouldComponentUpdate时，默认返回 true，所以组件都将重新渲染。
32. 在 context 中默认值的目的是什么?
	- A：当在组件树中的组件没有匹配到在其上方的 Provider 时，才会使用 defaultValue 参数。这有助于在不包装组件的情况下单独测试组件

		```jsx
		const defaultTheme = "Tom";
		const MyContext = React.createContext(defaultTheme); //这里停供了Tom作为默认值
		```
33. super()和super(props)有什么区别？
	- A：在ES6中是通过extends来实现类的继承，super()会调用父类的构造函数，super()的作用是形成子类的this对象，把父类的实例属性和方法放到这个this对象上面（继承父类的this对象），只有调用super()之后，才可以使用this关键字，否则会报错。
	
		> 在React的类组件是基于ES6规范实现的，因此如果用到constructor就必须写super()才初始化this。如果我们不用constructor时，React内部也会将其定义在组件实例中
		>
		> ```jsx
		> // React 内部
		> const instance = new YourComponent(props);
		> instance.props = props;
		> ```
		>
		> 那么super()和super(props)有什么区别呢？
		>
		> - 即使你调用 super()的时候没有传入props，你依然能够在render函数或其他方法中访问到this.props，React内部会在构造函数执行完毕后给this.props赋值（在这之前this.props为undefined）
		>
		> 	```jsx
		> 	class Button extends React.Component {
		> 	  constructor(props) {
		> 	    super(); // 没传入 props
		> 	    console.log(props);      //  {}
		> 	    console.log(this.props); //  undefined
		> 	  }
		> 	}
		> 	```
		>
		> - 而传入props则能在任何地方都能正常访问，确保了this.props在构造函数执行完毕之前已被赋值，更符合逻辑
		>
		> 	```jsx
		> 	class Button extends React.Component {
		> 	  constructor(props) {
		> 	    super(props); 
		> 	    console.log(this.props); //  {}
		> 	  }
		> 	}
		> 	```
34. 什么是调解?
	- A：当组件的props或state发生更改时，React通过将新返回的元素与先前呈现的元素进行比较来确定是否需要实际的 DOM 更新。当它们不相等时，React 将更新DOM 。此过程称为调解。
35. 说说对React refs 的理解？应用场景？
	- A：React 中的 `Refs`提供了一种方式，允许我们访问 `DOM `节点或在 `render `方法中创建的 `React `元素，本质为ReactDOM.render()返回的组件实例，如果是渲染组件则返回的是组件实例，如果渲染dom则返回的是具体的dom节点。

		> 类组件中ref的创建形式有三种
		>
		> - 传入字符串，使用时通过this.refs.传入的字符串的格式获取对应的元素
		>
		> 	```jsx
		> 	class MyComponent extends React.Component {
		> 	  constructor(props) {
		> 	    super(props);
		> 	    this.myRef = React.createRef();
		> 	  }
		> 	  render() {
		> 	    return <div ref="myref" />;
		> 	  }
		> 	}
		> 	//访问
		> 	this.refs.myref.innerHTML='haha';
		> 	```
		>
		> - 传入对象，对象是通过React.createRef()方式创建出来，使用时获取到创建的对象中的current属性就是对应的元素。
		>
		> - 传入函数，该函数会在 DOM 被挂载时进行回调，这个函数会传入一个元素对象，可以自己保存，使用时，直接拿到之前保存的元素对象即可
		>
		> 	```jsx
		> 	class MyComponent extends React.Component {
		> 	  constructor(props) {
		> 	    super(props);
		> 	    this.myRef = React.createRef();
		> 	  }
		> 	  render() {
		> 	    return <div ref={element => this.myref = element} />;
		> 	  }
		> 	}
		> 	//获取
		> 	const node = this.myrf
		> 	```
		>
		> 在函数组件中可以通过hook创建对象，并获取节点
		>
		> ```jsx
		> function App(){
		>    const myRef = useRef(null);
		>    return <div ref={myRef}></div>
		> }
		> //同样通过current属性来对应节点
		> ```
		>
		> 使用方面：过多使用`refs`，会使组件的实例或者是`DOM`结构暴露，违反组件封装的原则，更多情况我们是通过`props`与`state`的方式进行去重新渲染子元素。但在DOM元素的焦点控制、内容选择、媒体控制、内容设置等场景还是很有效的
36. 什么是上下文（Context）?
	- A：Context通过组件树提供了一个传递数据的方法（通过createContext创建一个上下文，并通过Provider包裹所有可能使用对应value的组件），从而避免了在每一个层级手动的传递`props`（在后代组件中可以通过useContext来获取对应上下文种的数据）。比如，需要在应用中许多组件需要访问登录用户信息、地区偏好、UI主题等。
37. React的displayName有什么作用？
	- A：在React中，displayName是一个静态属性，用于给组件设置一个可读性更好的显示名称。它对于开发者来说是可选的，没有直接的功能影响，但在开发和调试过程中具有一定的重要性。

		```jsx
		//类组件中
		class MyComponent extends React.Component {
		  // 组件代码...
		  
		  static displayName = 'MyComponent';
		}
		
		//函数组件中
		const MyComponent = () => {
		  // 组件代码...
		};
		
		MyComponent.displayName = 'MyComponent';
		```
38. Hooks 需要遵循什么规则?
	- A：
		- 只能在React组件或自定义hook的最顶层调用hooks。也就是说，你不能在循环、条件或内嵌函数中调用 hooks。这将确保每次组件渲染时都以相同的顺序调用 hooks，并且它会在多个 useState 和 useEffect 调用之间保留 hooks 的状态。
		- 仅在 React 函数组件中调用 hooks。例如，你不能在常规的 JavaScript 函数中调用 hooks。
39. React memo 函数是什么?
	- A：默认情况下如果父组件重新渲染，那么该父组件下的所有子组件都会随着父级的重新渲染而重新渲染，使用React.memo仅仅是让该函数组件具备了可以跳过本次渲染的基础，当子组件中props没有发生变化时可以跳过本次渲染。
	
		```jsx
		const MyCmt = React.memo((props)=>{
		   //do Something
		})
		export MyCmt
		```
	
	- 我们可以将memo看做一个高阶函数，接收一个组件作为参数，并且返回一个包装过的新组组件，包装过的组件具有缓存功能，只有props变化会使子组件重新渲染，否则总返回缓存中的结果
40. ref 参数对于所有函数或类组件是否可用?

	- A：常规函数或类组件不会接收到ref参数，并且ref在props中也不可用。只有在使用 React.forwardRef定义组件时才存在第二个为ref的参数。
41. 在react中组件间过渡动画如何实现？
	- A：组件的过渡动画就是页面切换时组件的显示与消失中的一个过渡效果，它可以增加用户的体验。在react中实现过渡动画效果通常可以使用`react-transition-group`，`react-motion`，`Animated`，以及原生的`CSS`都能完成切换动画。

		> 其中react-transition-group是一种很好的解决方案，其为元素添加`enter`，`enter-active`，`exit`，`exit-active`这一系列勾子来帮助我们实现组件显示和消失的动画。
		>
		> - CSSTransition：结合CSS来完成过渡动画效果，其实现在于CSSTransition的`in`属性为`true`时，会给其子组件添加`xxx-enter`、`xxx-enter-active`的class执行动画，动画结束后移除前两个class并添加`xx-enter-done`的class。当`in`属性置为`false`时，与ture过程相同只是class由`enter`变为`exit`。
		>
		> 	```jsx
		> 	//这里使用css module引入
		> 	import styles from "./styles.module.scss";
		> 	import { CSSTransition, SwitchTransition } from "react-transition-group";
		> 	export default function AnimationExample(){
		> 	   const [show, setShow] = useState(true);
		> 	   return(
		> 	      <Button type="primary" onClick={() => setShow(!show)}>切换</Button>
		> 	      <CSSTransition
		> 	        in={show}
		> 	        timeout={500}
		> 	        classNames={{
		> 	          enter: styles.fadeEnter,
		> 	          enterActive: styles.fadeEnterActive,
		> 	          enterDone: styles.fadeEnterDone,
		> 	          exit: styles.fadeExit,
		> 	          exitActive: styles.fadeExitActive,
		> 	          exitDone: styles.fadeExitDone,
		> 	        }}>
		> 	        <div className={styles.box}></div>
		> 	      </CSSTransition>。
		> 	   ) 
		> 	}
		> 	//也可以使用类名前缀写法，但要指定全局样式
		> 	<CSSTransition in={show} unmountOnExit={true} timeout={500} classNames={"fade"}>
		> 	    <div className={styles.box}></div>
		> 	</CSSTransition>
		> 	//其中unmountOnExit表示当in从ture变为false动画结束后是否在页面中移除该DOM
		> 	//timeout是xx-enter和xx-enter-active（或者xx-exit和 xx-exit-active）的作用时间
		> 	```
		>
		> 	```css
		> 	.fade-enter {
		> 	  opacity: 0;
		> 	  transform: translateX(100%);
		> 	}
		> 	
		> 	.fade-enter-active {
		> 	  opacity: 1;
		> 	  transform: translateX(0);
		> 	  transition: all 0.5s;
		> 	}
		> 	.fade-enter-done {
		> 	  /* ... */
		> 	}
		> 	.fade-exit {
		> 	 /* ... */
		> 	}
		> 	
		> 	.fade-exit-active {
		> 	 /* ... */
		> 	}
		> 	.fade-exit-done {
		> 	 /* ... */
		> 	}
		> 	```
		>
		> - SwitchTransition：可以完成两个组件之间切换的动画效果，它有一个`mode`属性对应`in-out`表示新组件先进入旧组件再移除、`out-in`则与之相反。需要配合`CSSTransition`使用，且`CSSTransition`组件不再像以前那样接受`in`属性来判断元素是何种状态，取而代之的是`key`（string类型）属性，key来判断否需要触发动画。
		>
		> 	```jsx
		> 		import { CSSTransition, SwitchTransition } from "react-transition-group";
		> 	export default function AnimationExample(){
		> 	   const [isOn, setIsOn] = useState(true);
		> 	   return(
		> 	   	<div>
		> 	      <SwitchTransition mode="out-in">
		> 	      	 <CSSTransition
		> 	        	key={isOn ? "on" : "off"}
		> 	        	timeout={500}
		> 	        	classNames={'fade'}>
		> 	        	<button onClick={()=>setIsOn(!isOn)}>
		> 	            	{isOn ? "on": "off"}
		> 	          	</button>
		> 	      	</CSSTransition>。   	 
		> 	      </SwitchTransition>
		> 	    </div>
		> 	  ) 
		> 	}
		> 	```
		> 
		>- TransitionGroup：用于列表项的过渡动画，它本身不提供任何形式的动画，同样需要配合CSSTransition使用。在处理上对于插入的节点先渲染dom、再执行动画，对于删除的节点先执行动画、在删除dom
42. 请说说什么是useEffect？
	- A：它是一个Hook，让我们在渲染后运行一些代码使你的组件与 React 之外的一些系统同步等操作来处理副作用，`useEffect`会“延迟”一段代码的运行，直到该渲染反映在屏幕上，且默认情况下每次组件的重新渲染useEffect都会重新执行，useEffect 可以看做是 `componentDidMount/componentDidUpdate/componentWillUnmount` 这三个生命周期函数的替代

		> 第一个参数是函数，第二个参数是依赖的数据数组，当配置依赖数组后只有当数组中数据发生变化时，才会使其重新执行。
		>
		> 它可以通过return返回一个清理函数，用于指定如何停止、撤消或清理它们正在做的任何事情（获取数据、发送请求），清理函数会在下一次Effect执行之前被调用，可以通过清理函数来清除上一次effect带来的副作用，类似与类组件中componentWillUnmount。
43. 说说你对React Router的理解？常用的Router组件有哪些？ 

	- A：`react-router`等前端路由的原理大致相同，可以实现无刷新的条件下切换显示不同的页面。其本质就是URL发生改变时页面显示结果根据URL的变化而改变，因此路由可以实现单页面应用（在一个html文件中进行内容切换渲染，你看见的其它页面都是js生成的， 地址栏url的变化是js去改变）

		> react-router分为几个不同的包：
		>
		> 1. react-router：实现路由的核心功能
		> 2. react-router-dom： 基于react-router，加入了在浏览器运行环境下的一些功能
		> 3. react-router-native：基于 react-router，加入了 react-native 运行环境下的一些功能
		> 4. react-router-config: 用于配置静态路由的工具库
		>
		> 常用组件：
		>
		> 1. BrowserRouter、HashRouter：Router中包含了url路径变化的监听，并且会将相应的路径传递给子组件。BrowserRouter使用的是history模式，HashRouter使用的是hash模式
		> 2. Route：Route用于路径的匹配，然后进行组件的渲染，常用属性有：
		> 	- path：用于设置匹配路径
		> 	- component：当url与path匹配时要渲染什么组件
		> 	- render：当url与path匹配时要渲染的内容
		> 	- exact：开启精确匹配，只有url和path完全一致才会渲染对应组件
		> 3.  Link、NavLink：通常路径的跳转是使用Link组件，最终会被渲染成`a`元素，其中属性`to`代替`a`标题的`href`属性。`NavLink`是在`Link`基础之上增加了一些样式属性，比如当某个组件选中时为链接设置被激活的状态样式以及类名
		> 3.  redirect：用于路由的重定向，当这个组件出现时，就会执行跳转到对应的`to`路径中
		>
		> 常用常用hook：
		>
		> 1. useParams：获取获取URL中携带过来的params参数
		>
		> 	```jsx
		> 	<Routes>
		> 	 <Route path='about/:id' element=<About/> />
		> 	</Routes>
		> 	
		> 	function About(){
		> 	  const{id} = useParams();  //获取url中以id定义为参数的值
		> 	}
		> 	```
		>
		> 2. useLocation：用于获取当前路径的信息，它返回一个包含pathname、search等属性的对象
		>
		> 路由传递参数主要分为三种形式：
		>
		> - 动态路由的方式：指路由中的路径并不固定，如比path在Route匹配时写成`/detail/:id`，那么 `/detail/abc`、`/detail/123`都可以匹配到该Route
		> - search传递参数：在跳转的路径中添加了一些查询字符串
		> - 在Link组件的to中传入一个包含url信息的对象
44. 说说React Router有几种模式？实现原理？

	- A：在单页面应用中，一个web项目只有一个html页面，一旦页面加载完成之后，就不用因为用户的操作而进行页面的重新加载或者跳转。

		> 路由描述了URL与组件之间的映射关系，这种映射是单向的，即URL变化导致渲染不同的组件
		>
		> 特性如下：
		>
		> - 改变url也不会让浏览器向服务器发送请求
		> - 可以在不刷新页面的前提下动态改变浏览器地址栏中的URL地址
		>
		> React中路由分为两种模式：
		>
		> - hash模式：hash模式会在url后面加上#，如http://127.0.0.1:5500/home/#/page1。
		> 	hash值的改变会触发window对象上的`hashchange` 事件，hash模式就是利用`hashchange` 事件监听`hash`值的变化来改变`URL` ，通过`context`将`location`数据往后代组件传递，通过props将Route组件中的path与location.pathname进行匹配，来决定是否渲染组件
		> - history模式：允许操作浏览器曾经在标签页或者框架里访问的会话历史记录
		> 	通过使用history对象+h5的pushState实现的（route组件通过listen监听路由变化）
45. react-router 里的 \<Link> 标签和 \<a> 标签有什么区别？
	- A：

		- 对比 \<a> 标签，Link避免了不必要的重新渲染。react-router接管了其默认的链接跳转行为，与传统的页面跳转有区别的是，Link的跳转只会触发相匹配的对应的页面内容更新，而不会刷新整个页面。

			> Link 做了三件事情：
			>
			> 1. 有click事件绑定，就执行对应处理函数
			> 2. 阻止a标签默认事件
			> 3. 根据跳转href，用history跳转，此时只是链接变了，并没有刷新页面

		- 而\<a>就是普通超链接标签，用于从当前页面跳转到href指向的另一个页面
46. 什么是渲染属性?
	- A：Render Props 是一种简单的技术，用于使用值为函数的prop属性在组件之间共享代码，许多库都使用了这种模式

		```jsx
		<DataProvider render={data => (
		  <h1>{`Hello ${data.target}`}</h1>
		)}/>
		```
47. 说说React render方法的原理？在什么时候会被触发？
	- A：

		- render在类组件和函数组件中存在的像是不同，在类数组中指的是render方法、在函数组件中指函数本身，在render中我们编写jsx并且最终由babel编译转化为浏览器可识别的js。render过程中，React将新调用的render函数返回的树与旧树进行比较，来判断是否需要更新DOM，然后进行diff比较更新DOM树。
		- 类组件中通过setState修改状态、函数组件中通过useState返回的第二个参数来更新状态触发render

		> render函数里面编写JSX，并转换为createElemet这种形式，最终转化为真实DOM。React中类组件只要通过setState方法修改状态默认情况下都会使render方法执行，函数组件使用useState更改状态不一定会导致render重新执行（useState会判断当前值有无发生改变）。
		>
		> 其次props的改变不一定触发render的执行，但是如果props的值来自于父组件或者祖先组件的state，在这种情况下，父组件或者祖先组件的state发生了改变，就会导致子组件的重新渲染。
48. 如何有条件地渲染组件?

	- A：在某些情况下，我们会根据某些状态渲染不同的组件。 JSX不会渲染false或undefined，因此使用 `&&` 运算符，在某个条件为 true 时，渲染组件中指定的内容。

		```jsx
		const MyComponent = ({ name, address }) => (
		  <div>
		    <h2>{name}</h2>
		    {address &&
		      <p>{address}</p>
		    }
		  </div>
		)
		```

		对于判断而言我们可以使用if-else，也可以使用三元运算符

		```jsx
		const MyComponent = ({ name, address }) => (
		  <div>
		    <h2>{name}</h2>
		    {address
		      ? <p>{address}</p>
		      : <p>{'Address is not available'}</p>
		    }
		  </div>
		)
		```
49. Router中history的 `push()` 和 `replace()` 方法的目的是什么?
	- A：一个 history 实例有两种导航方法`push()`、`push()`。如果您将 history 视为一个访问位置的数组，则`push()`将向数组添加一个新位置，`replace()`将用新的位置替换数组中的当前位置。
	
		> React Router是`history`库的包装器，它处理浏览器的`window.history`与浏览器和哈希历史的交互。它还提供了内存历史记录，这对于没有全局历史记录的环境非常有用，例如移动应用程序开发（React Native）和使用 Node 进行单元测试。
50. useEffect 的第二个参数, 传空数组和传依赖数组有什么区别？

	- A：在 React 中，useEffect 是一个常用的 Hook，它用于处理组件生命周期中的副作用。useEffect接收两个参数，第一个参数是一个函数表示要执行的操作，第二个参数是一个依赖数组（可选）

		> 当依赖数组为空数组 [] 时，useEffect 只会在组件挂载和卸载时调用一次。这种情况下，useEffect 不会监听任何变量，并且不会对组件进行重新渲染。
		>
		> ```jsx
		> useEffect(() => {
		>   // 只在挂载和卸载时执行
		> }, []);
		> ```
		>
		> 当依赖数组中有参数时，useEffect 会在组件挂载和依赖项更新时调用。当依赖项中的任何一个值发生变化时，useEffect 都将被重新调用。如果依赖数组为空，则每次组件重新渲染时都会调用 useEffect。
		>
		> ```jsx
		> useEffect(() => {
		>   // 在挂载、依赖列表变化及卸载时执行
		> }, [dep1, dep2]);
		> ```

		使用useEffect时，应该确保其内部使用的所有变量都在依赖项中被显示声明，否则可能会导致不必要的重新渲染或者无法获取最新的状态。
51. 在 React 中什么是渲染劫持?
	- A：渲染劫持的概念是控制一个组件将从另一个组件输出什么的能力。实际上，这意味着你可以通过将组件包装成高阶组件来装饰组件。通过包装，你可以注入额外的属性或产生其他变化，这可能会导致渲染逻辑的更改。实际上它不支持劫持，但通过使用 HOC，你可以使组件以不同的方式工作。