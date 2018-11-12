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
	
	