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
