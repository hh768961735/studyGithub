### 1、display:none和visibility:hidden的区别？
	display:none  隐藏对应的元素，在文档布局中不再给它分配空间，它各边的元素会合拢，
	就当他从来不存在。
	visibility:hidden  隐藏对应的元素，但是在文档布局中仍保留原来的空间。
### 2、CSS中 link 和@import 的区别是？
	(1) link属于HTML标签，而@import是CSS提供的; 
	(2) 页面被加载的时，link会同时被加载，而@import引用的CSS会等到页面被加载完再加载;
	(3) import只在IE5以上才能识别，而link是HTML标签，无兼容问题;
	 (4) link方式的样式的权重 高于@import的权重.
### 3、position的absolute与fixed共同点与不同点
	A：共同点：
	1.改变行内元素的呈现方式，display被置为block；
	2.让元素脱离普通流，不占据空间；3.默认会覆盖到非定位元素上
	B不同点：
	absolute的”根元素“是可以设置的，而fixed的”根元素“固定为浏览器窗口。
	当你滚动网页，fixed元素与浏览器窗口之间的距离是不变的。  
### 4、介绍一下CSS的盒子模型？
	1）有两种， IE 盒子模型、标准 W3C 盒子模型；IE的content部分包含了 border 和 pading;

	2）盒模型： 内容(content)、填充(padding)、边界(margin)、 边框(border).
### 5、CSS 选择符有哪些？哪些属性可以继承？优先级算法如何计算？ CSS3新增伪类有那些？
	 1.id选择器（ # myid）
      	  2.类选择器（.myclassname）
       	 3.标签选择器（div, h1, p）
       	 4.相邻选择器（h1 + p）
       	 5.子选择器（ul > li）
      	  6.后代选择器（li a）
       	 7.通配符选择器（ * ）
       	 8.属性选择器（a[rel = "external"]）
       	 9.伪类选择器（a: hover, li:nth-child）
	==========
	*   可继承的样式： font-size font-family color, text-indent;  	 
	*   不可继承的样式：border padding margin width height ;
   	*   优先级就近原则，同权重情况下样式定义最近者为准;
  	*   载入样式以最后载入的定位为准;
	==========
	优先级为:
	 !important >  id > class > tag  
	 important 比 内联优先级高,但内联比 id 要高
	==========
	CSS3新增伪类举例：
	p:first-of-type 选择属于其父元素的首个 <p> 元素的每个 <p> 元素。
	p:last-of-type  选择属于其父元素的最后 <p> 元素的每个 <p> 元素。
	p:only-of-type  选择属于其父元素唯一的 <p> 元素的每个 <p> 元素。
	p:only-child    选择属于其父元素的唯一子元素的每个 <p> 元素。
	p:nth-child(2)  选择属于其父元素的第二个子元素的每个 <p> 元素。
	:enabled  :disabled 控制表单控件的禁用状态。
	:checked        单选框或复选框被选中。

### 6、列出display的值，说明他们的作用。position的值， relative和absolute分别是相对于谁进行定位的？
	1、
	block 象块类型元素一样显示。
 	inline 缺省值。象行内元素类型一样显示。
	inline-block 象行内元素一样显示，但其内容象块类型元素一样显示。
	list-item 象块类型元素一样显示，并添加样式列表标记。
	2、
	 *absolute 
        		生成绝对定位的元素，相对于 static 定位以外的第一个祖先元素进行定位。 
	  *fixed （老IE不支持）
        		生成绝对定位的元素，相对于浏览器窗口进行定位。 

	  *relative 
        		生成相对定位的元素，相对于其在普通流中的位置进行定位。 
	  * static  默认值。没有定位，元素出现在正常的流中
  	  *（忽略 top, bottom, left, right z-index 声明）。
	  * inherit 规定从父元素继承 position 属性的值。
### 7、div水平垂直居中
			body,html{
				margin: 0;
				padding: 0;
			}
			.vh{
				height: 200px;
				width: 200px;
				top: 50%;
				left: 50%;
				margin-left: -100px;
				margin-top: -100px;
				position: absolute;
				background-color: color;
			}	
### 8、清除浮动的放法
	1、父级div定义height
	2、结尾处添加空的div标签 clear:both
	3、父级div定义伪类：after和zoom
	4、父级div定义 overflow:hidden