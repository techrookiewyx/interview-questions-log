## HTML部分

1. 如何在HTML中创建一个链接？
	- A：可以使用`<a>`标签来创建一个链接。如`<a href="https://www.example.com">Click here</a> `
	- 解析：`<a>`标签是HTML中用于创建超链接的标签，其最常见的属性为`href`用于用于指定链接的目标URL。
2. 如何在HTML中插入一张图片？
	- A：使用`<img>`标签来插入一张图片。例如：`<img src="image.jpg" alt="Image">`。
	- 解析：`<img>`标签是HTML中用于插入图片的标签。src属性用于指定图片的URL，alt属性用于指定图片的替代文本（当图片无法显示时会显示该文本）。
3. 如何在HTML中创建一个无序列表？
	- A：使用`<ul>`和`<li>`标签来创建无序列表。
	- 解析：在HTML中常用列表有`<ul>`无序列表、`<ol>`有序列表和`<dl>`自定义列表，`<li>`标签则表示列表中的列表项（ul和ol中使用）。
4. 请说一下HTML5有哪些新特性
	- A：HTML5是HTML的第五个版本，新特性包括语义化标签（如`header`、`<nav>`、`<footer>`等），表单增强（如新的输入类型、表单验证等）音视频支持（如`<video>`、`<audio>`标签）,本地存储（如localStorage、sessionStorage）等。
5. 请说一说HTML中的meta标签
	- A：`meta`标签用于提供一些关于HTML文档的元数据（描述数据的数据）。常见的`meta`标签包括charset（指定文档的字符编码）、viewport（指定视口的大小和缩放比例）、description（指定网页的描述信息）等。`meta`标签可以通过name和content属性来定义元数据。
		```html
		<!-- 定义文档编码字符集 -->
		<meta charset="utf-8">
		<!-- 设置视口的大小为300px -->
		<meta name="viewport"  content="Width:300px">
		```
	- 解析：meta标签是前端开发中常用的一种标签，meta标签的使用对于优化网页的SEO和用户体验非常重要。
6. 请解释一下HTML中的语义化标签。
	- A：语义化标签通俗来说就是可以直接知道该标签代表什么（指具有特定含义和作用的标签）。语义化标签可以使页面的结构更加清晰和易于理解，同时也有利于搜索引擎的优化和可访问性。
7. 网页抽象成三部分（HTML、CSS和JavaScript）后的优点有哪些？ 
	- A：三部分是HTML代表结构负责页面内容和结构、CSS代表表现负责内容样式、JS表示行为负责页面动态交互。
		抽象为三部分可以`增加代码可读性`、`按需加载资源`、`便于后期维护`。
8. HTML5删除和新增了哪些元素
	- A：新增了`article`、`header`等内容元素，`data`、`time`、`number`等表单元素，`video`、`audio`多媒体元素，`<canvas>`绘图元素等。移除了`<applet>`、`<basefont>`、`<big>`、`<center>`、`<font>`、`<frame>`等元素。

