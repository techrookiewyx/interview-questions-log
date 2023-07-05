## CSS部分

1. 如何将一个元素居中显示？
	- A：可以使用CSS的`margin`属性来实现居中显示。例如：`margin: 0 auto;`
	- 解析：`margin`属性用于设置元素的外边距，通过将左右外边距设置为`auto`，可以将元素水平居中显示。前提是该元素具有可计算的宽度
2. 如何实现一个水平导航栏？
	- A：可以使用CSS的`display: flex;`和`justify-content: space-between;`来实现水平导航栏
		```css
		.nav{
		  display: flex;
		  justify-content: space-between;
		}
		```
	- 解析：`display: flex;`用于将一个元素设置弹性容器，设置该属性后容器下所有直接子元素默认水平排列，`justify-content: space-between;`将子元素平均分布在容器内，实现水平导航栏的效果。
3. 如何实现一个响应式布局?
	- A：可以使用CSS的媒体查询（`@media`）来实现响应式布局，如下例
		```css
		@media (max-width: 768px){
		   /*当屏幕或页面宽度小于768px时应用如下样式*/
		    .container{ flex-direction: colum; }
		}
		```
	- 解析：媒体查询是CSS中用于根据设备的特性（如屏幕宽度）来应用不同的样式的机制，可以在不同的屏幕宽度下应用不同的样式，从而实现响应式布局。
4. 说一下CSS盒模型
	- A：CSS盒模型是将一个元素看成一个盒子，用来描述HTML元素在页面中所占空间的模型。它包括了内容区域（content）、内边距（padding）、边框（border）和外边距（margin）四个部分
