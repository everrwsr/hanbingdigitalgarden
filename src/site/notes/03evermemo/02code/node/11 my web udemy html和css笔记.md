---
{"dg-publish":true,"permalink":"/03evermemo/02code/node/11-my-web-udemy-html-css/"}
---




udemy html和css 
html中间html元素不但代表外观样式的好看与否
在html5中，更加强调html元素的语义
div
与
Nav article header footer
效果相同
但是
我们为了让这个更有意义
选择了nav这些标签，更关键一点是方便seo优化
css 选择器有三类
````

p{}          样式选择器    不太常用啦
#yuyu{}   id 选择器          同名的只可以用一次
.class {}    类选择器       同名的可以放多次

---------
元素选择器（也称作标签或类型选择器）	所有指定 (该) 类型的 HTML 元素	p 选择 <p>
ID 选择器	具有特定 ID 的元素（单一 HTML 页面中，每个 ID 只对应一个元素，一个元素只对应一个 ID）	#my-id 选择 <p id="my-id"> 或 <a id="my-id">
类选择器	具有特定类的元素（单一页面中，一个类可以有多个实例）	.my-class 选择 <p class="my-class"> 和 <a class="my-class">
属性选择器	拥有特定属性的元素	img[src] 选择 <img src="myimage.png"> 而不是 <img>
伪（Pseudo）类选择器	特定状态下的特定元素（比如鼠标指针悬停）	a:hover 仅在鼠标指针悬停在链接上时选择 <a>。
----------------------------


优先级 id >>  类  >> 样式
如果是同级别        越在后面越是优先
特殊情况需要提高你的优先级  
在强调的那个属性那里加上  ！important


udemy html css
课程大纲
1. html 基础
2. css  基础
3. flex 
4. 网页设计与框架
5. 组件和布局模式
6. 实践 omnifood 项目
```
