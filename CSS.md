
# 是什么
>CSS （Cascading Style Sheets 层叠样式表） 给网页 设置样式和布局；
 - 修改内容的字体、颜色、大小、间距；
 - 内容多少列；
 - 添加动画
 - 其他装饰功能

## 语法是什么
> 基于规则的语言——你能定义用于你的网页中特定元素样式的一组规则


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

## CSS模块
通过 CSS 为许多东西添加样式，CSS 由许多模块（module）构成

## CSS 规范
> 用户代理是代表一个人的计算机程序，例如，一个在 Web 上的 浏览器。

它（规范）旨在为工程师在用户代理 (user agents) 中实现对 CSS 各种特性的支持，而不是作为一本为 Web 开发者理解 CSS 内容的教程

## 浏览器支持
CSS特性兼容

# 如何使用
## 在HTML中的应用
- 外部样式表： xxx.css 文件，被html文档引用；可以同时引用多个外部样式表；通过`<link>`标签的`href`属性， 写法如`<link rel="stylesheet" href="styles/style.css" />
`

- 内部样式表：写在html同一个文件的样式；在`<head>`标签内定义 `<style>`元素，

- 内联样式表：是影响单个 HTML 元素的 CSS 声明，包含在元素的 style 属性中， 如` <p style="color:red;">这是我的第一个 CSS 示例</p>`; <b>尽可能避免以这种方式使用 CSS</b>，这不符合最佳实践;

# 选择器
>选择器以 HTML 为目标，对内容应用样式
每个 CSS 规则都以一个选择器或一组选择器为开始，去告诉浏览器这些规则应该应用到哪些元素上

## 不同类型的选择器
选择器有许多不同的类型。上面只介绍了元素选择器，用来选择 HTML 文档中给定的元素。但是选择操作可以更加具体。下面是一些常用的选择器类型：
选择器名称	                               选择的内容	     示例
元素选择器（也称作标签或类型选择器）	所有指定类型的 HTML 元素	p 选择 <p>

ID 选择器	具有特定 ID 的元素。单一 HTML 页面中，每个 ID 只对应一个元素，一个元素只对应一个 ID	#my-id
选择 `<p id="my-id">` 或 `<a id="my-id">`

类选择器	具有特定类的元素。单一页面中，一个类可以有多个实例	.my-class
选择 `<p class="my-class"> `和 `<a class="my-class">`

属性选择器	拥有特定属性的元素	img[src]
选择 `<img src="myimage.png">` 但不是 `<img>`

伪类选择器	特定状态下的特定元素（比如鼠标指针悬停于链接之上）	a:hover
选择仅在鼠标指针悬停在链接上时的 `<a> `元素

## 优先级
CSS 语言有一些规则来控制在发生冲突的情况下哪个选择器更强大。这些规则被称为层叠（cascade）和优先级（specificity）
- 写在最后的规则优先级更高
  
## 属性和值
CSS 由两个组成部分组成：
- 属性：人类可读的标识符，指示想要更改的样式特征。如 font-size、width、background-color。
- 值：每个指定的属性都有一个值，这个值表示如何对属性施加样式。
当一个属性与一个值配对时，这种配对被称为 CSS 声明
![Alt text](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/First_steps/How_CSS_is_structured/declaration-block.png)
CSS 声明可以在 CSS 声明块中找到。在上面的例子中，高亮显示的是 CSS 声明块。

最后，CSS 声明块与选择器配对，以生成 CSS 规则集（或称 CSS 规则）。这个示例包含两个规则，一个用于 h1 选择器，另一个用于 p 选择器。h1 的规则被突出显示。
![Alt text](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/First_steps/How_CSS_is_structured/rules.png)
将CSS属性设置为特定值是定义文档布局合格样式的主要方式，CSS引擎会计算哪些声明适用于页面的每一个元素；

**注意**：
- 属性和值区分大小写，中间有`:`分隔；
- 属性未知或值对给定属性无效，则声明被视为 **无效**
- 当语言表达存在不确定性时，美式拼写被视作公认的标准。例如，“颜色”应该始终拼写为 color，colour 是不起作用的。

## 函数
属性和值大多数死关键字和数值，但也有些值是一函数的形式出现；
**calc()函数** 
允许在CSS中进行简单计算「[链接]([http://链接网址](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/First_steps/How_CSS_is_structured))」
```css
.box {
  width: calc(90% - 30px);
}
```
函数由函数名和括号组成，括号内是函数的值;
**Transform函数**

## @规则
`@rules` 一些特殊的规则，提供了关于CSS应该执行什么货如何表现的指令；
有些@规则很简单，只有一个关键词和一个值。例如，@import 将一个样式表导入另一个 CSS 样式表：
```css
@import "styles2.css";
```
常见的@规则是 @media:
```css
body {
  background-color: pink;
}

@media (min-width: 30em) {
  body {
    background-color: blue;
  }
}

```

# 简写属性
# 注释

## CSS：一切皆盒子
CSS 布局主要是基于盒子模型。在你的页面上占用空间的每个盒子都有类似的属性：

padding（内边距）：是指内容周围的空间。在下面的例子中，它是段落文本周围的空间。
border（边框）：是紧接着内边距的线。
margin（外边距）：是围绕元素边界外侧的空间。

