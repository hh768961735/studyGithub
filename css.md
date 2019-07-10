### 盒子模型
#### content
#### padding
	-盒子内容与边框之间的距离
	padding-top,padding-left,padding-right,padding-bottom
	content的颜色与padding的颜色相同
#### border
	- 设置四个值则分别为上、右、下、左的宽度
	- 设置三个值则分别为上、左右、下的宽度
	- 设置两个值则分别为上下、左右的宽度
	border-width:10px 20px 30px 40px;
	- 颜色同上
	border-color:
	- none:默认无边框
	- solid:实线
	- dotted:点状边框
	- dashed:虚线边框
	- double:双线
	- 样式设置同上
	border-style:
	======
	border:10px red solid;
	- 可以直接设定三个属性
	border-top,border-left,border-right,border-bottom可分别设定各边属性
#### margin
	垂直外边距重叠
	- 相邻的垂直兄弟元素之间外边距取最大值
	- 若父子元素的垂直外边距相邻，则子元素的外边距会传递给父元素
### 内联元素(span)
	- 内联元素不能设置height和width
	- 可以设置水平和垂直方向(bottom)的内边距，并且垂直不会影响页面布局
	- 可以设置边框，并且不会影响页面布局
	- 可以设置外边距，水平外边距可以叠加，不支持垂直外边距
#### display
	- inline:将一个元素变为内联元素
	- block:将一个元素变为块元素
	- inline-bolck:可以使一个元素变为行内块元素，既可以是行元素也可以是块元素
	- none:不显示元素,并且不再占用位置
#### visibility
	- visible:默认值
	- hidden:元素不显示，但是会占用位置	
#### overflow
	- 如果子元素在父元素中溢出时，使用overflow处理
	- visible:默认值
	- hidden:溢出的内容会被隐藏
	- scroll:溢出的内容会隐藏在滚动条中
	  无论内容是否溢出，都会显示滚动条
	- auto:自动设置是否需要滚动条
### 文档流
	- 块元素在文档流中独占一行，自上向下排列
		默认宽度是父元素的100%
		默认高度为子元素的高度
	- 内联元素在文档流中只占自身大小，自左向右排列，如果一行不够，则会换行，还是自左向右
		宽度和高度都由内容决定
### 浮动
	- 块元素在文档流中默认垂直排列，可以用float使其脱离文档流水平排列
	- 元素在脱离文档流后会尽量向页面左上或者右上浮动，直到遇到父元素的边框或者其他浮动元素
	- 浮动元素不会超过他上面的兄弟元素
	- 浮动元素不会盖住文字，文字自动环绕浮动周围
	- 块元素脱离文档流后，高度和宽度由内容决定
	- 内联元素脱离文档流后变成块元素
### 高度塌陷
	- 为子元素设置浮动后，会脱离文档流，导致父元素塌陷，父元素下的所有元素都会发生变化，为了避免这个问题
	- W3C标准中页面的隐藏属性BFC默认是关闭的
	- 当开启元素的BFC后会具有一下特性
	- 1.父元素的垂直外边距不会与子元素的重叠
	- 2.开启BFC的元素不会被浮动元素覆盖
	- 3.开启BFC的父元素可以包含浮动的子元素
	开启元素BFC的方法：
	1.设置元素浮动
	 这种方式会导致父元素宽度丢失，切下面的元素依旧会上移
	2.设置绝对定位
	3.设置元素为inline-block
	 这种方式会导致父元素宽度丢失
	4.将overflow设置为非visiable
	 最好的方式设置为hidden
	在IE6及以下的浏览器不支持FBC，可以开启hasLayout来解决问题
	所以可以同时使用overflow和zoom兼容所有浏览器
#### 高度塌陷最终解决方案
	clear:清楚其他浮动元素对当前元素的影响
	- 在高度塌陷的父元素最后添加一个空白的div，添加clear可以解决这个问题
	但是这种方式会添加多余的代码结构
	==========
	通过after伪类添加一个div
	.box1:after{
				content: "";
				display: block;
				clear: left;
			}
### 面试题
####1、display:none和visibility:hidden的区别？
	display:none  隐藏对应的元素，在文档布局中不再给它分配空间，它各边的元素会合拢，
	就当他从来不存在。
	visibility:hidden  隐藏对应的元素，但是在文档布局中仍保留原来的空间。
#### 2、CSS中 link 和@import 的区别是？
	(1) link属于HTML标签，而@import是CSS提供的; 
	(2) 页面被加载的时，link会同时被加载，而@import引用的CSS会等到页面被加载完再加载;
	(3) import只在IE5以上才能识别，而link是HTML标签，无兼容问题;
	 (4) link方式的样式的权重 高于@import的权重.
#### 3、position的absolute与fixed共同点与不同点
	A：共同点：
	1.改变行内元素的呈现方式，display被置为block；
	2.让元素脱离普通流，不占据空间；3.默认会覆盖到非定位元素上
	B不同点：
	absolute的”根元素“是可以设置的，而fixed的”根元素“固定为浏览器窗口。
	当你滚动网页，fixed元素与浏览器窗口之间的距离是不变的。  
#### 4、介绍一下CSS的盒子模型？
	1）有两种， IE 盒子模型、标准 W3C 盒子模型；IE的content部分包含了 border 和 pading;

	2）盒模型： 内容(content)、填充(padding)、边界(margin)、 边框(border).
#### 5、CSS 选择符有哪些？哪些属性可以继承？优先级算法如何计算？ CSS3新增伪类有那些？
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

#### 6、列出display的值，说明他们的作用。position的值， relative和absolute分别是相对于谁进行定位的？
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
#### 7、div水平垂直居中
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
#### 8、清除浮动的放法
	1、父级div定义height
	2、结尾处添加空的div标签 clear:both
	3、父级div定义伪类：after和zoom
	4、父级div定义 overflow:hidden