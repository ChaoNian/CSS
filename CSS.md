
## “CSS 规则集”详解
![Alt text](https://developer.mozilla.org/zh-CN/docs/Learn/Getting_started_with_the_web/CSS_basics/css-declaration-small.png)
整个结构称为规则集（规则集通常简称规则），注意各个部分的名称：
选择器（Selector）
HTML 元素的名称位于规则集开始。它选择了一个或多个需要添加样式的元素（在这个例子中就是 <p> 元素）。要给不同元素添加样式，只需要更改选择器。

声明（Declaration）
一个单独的规则，如 color: red; 用来指定添加样式元素的属性。

属性（Properties）
改变 HTML 元素样式的途径（本例中 color 就是 <p> 元素的属性）。CSS 中，由编写人员决定修改哪个属性以改变规则。

属性的值（Property value）
在属性的右边，冒号后面即属性的值，它从指定属性的众多外观中选择一个值（我们除了 red 之外还有很多属性值可以用于 color ）。

注意其他重要的语法：

除了选择器部分，每个规则集都应该包含在成对的大括号里（{}）。
在每个声明里要用冒号（:）将属性与属性值分隔开。
在每个规则集里要用分号（;）将各个声明分隔开。

p {
  color: red;
  width: 500px;
  border: 1px solid black;
}


## 不同类型的选择器
选择器有许多不同的类型。上面只介绍了元素选择器，用来选择 HTML 文档中给定的元素。但是选择操作可以更加具体。下面是一些常用的选择器类型：
选择器名称	                               选择的内容	     示例
元素选择器（也称作标签或类型选择器）	所有指定类型的 HTML 元素	p 选择 <p>

ID 选择器	具有特定 ID 的元素。单一 HTML 页面中，每个 ID 只对应一个元素，一个元素只对应一个 ID	#my-id
选择 <p id="my-id"> 或 <a id="my-id">

类选择器	具有特定类的元素。单一页面中，一个类可以有多个实例	.my-class
选择 <p class="my-class"> 和 <a class="my-class">

属性选择器	拥有特定属性的元素	img[src]
选择 <img src="myimage.png"> 但不是 <img>

伪类选择器	特定状态下的特定元素（比如鼠标指针悬停于链接之上）	a:hover
选择仅在鼠标指针悬停在链接上时的 <a> 元素

## CSS：一切皆盒子
CSS 布局主要是基于盒子模型。在你的页面上占用空间的每个盒子都有类似的属性：

padding（内边距）：是指内容周围的空间。在下面的例子中，它是段落文本周围的空间。
border（边框）：是紧接着内边距的线。
margin（外边距）：是围绕元素边界外侧的空间。
