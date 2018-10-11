### 10.10
#### 六种数据类型
	String,Number,Null,undefined,Boolean五中基本数据类型 		Object一种引用数据类型 
#### 转义字符 "\"
 	alert("hello world!");
	\" 表示 "
	\n 换行
	\t 制表符
	alert("\\");
	\\ 输出一个\
### 10.11
#### 标识符
	1、标识符包涵数字、字母、_、$
	2、不能以数字开头
	3、不能是关键字和保留字
	4、一般是驼峰命名法
#### Number
	1.7976931348623157e+308  Number.MAX_VALUE	
	5e-324 			 Number.MIN_VALUE 
	如果number值超过了最大值 则会返回Infinity 表示正无穷
	Infinity和NaN的typeof都是数字类型Number
#### Null
	使用typeof检查null值返回object
	使用typeof检查undefined返回undefined
#### 强制类型转换
	1、对于Number和Boolean可以调用toString()
	null和undefined没有toString()
	但是可以用String()方法直接转换为字符串
	2、字符串转换为数字
	(1) 字符串中只含有数字则直接转换为数字
	(2) 字符串中含有非数字则转换为NaN
	(3) 字符串为空则转换为0
	3、布尔值转换为数字
	true->1
	false->0
	4、Null转换为数字
	null->0
	5、undefined转换为数字
	undefined->NaN
#### 含有数字和字母的字符串
	var a="123px";
	a=parseInt(a); //123
	var a="123.456px";
	a=parseFloat(a);//123.456
	====如果对非String使用parseInt()和parseFloat()	
	会先转换为String然后在操作
	var a=true;
	a=parerInt(a);//NaN
#### 其他的数值类型转换为布尔值
	1、数字类型转换为布尔值
	除了0和NaN返回false，其他返回true
	2、字符串转换为布尔值
	除了为空，其他都为true
	3、null和undefined都会转换为false
	4、object转换为true
### 运算符
#### 算数运算符
	加法运算
	1、对非Number值进行运算时，先将其转换为Number在进行计算
	2、任何数和NaN运算都得NaN
	3、两个字符串相加，进行字符串拼接
	4、任何值和字符串相加，先转换为字符串，在进行拼接
	5、可以为任意的数据类型加一个空字符串""将其转换为	String类型
	=====
	任何值进行- * /运算时，都会转换为Number
	可以通过-0，*1，/1将其他值转换为Number
#### 一元运算符
	可以对任意数据使用+，将其转换为Number