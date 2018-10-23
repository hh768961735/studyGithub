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
#### 自增
	var a=1;
	a++; 与原值相等
	++a; 等于自增以后的值
#### 自减
	a--; 与原值相等
	--a; 等于自减后的值
### 逻辑运算符  &&、||、!
#### 非运算
	1、对布尔值进行非运算，false边为true，true变为false
	2、对非布尔值进行运算，先将其转换为布尔值在进行运算
	3、对任意的数据类型进行两次非运算即可转换为布尔值
#### 与运算
	有false就返回false
#### 或运算
	有true就返回true
### 非布尔值的逻辑运算
#### 与运算
	1、对于非布尔值的逻辑运算，先将其转换为布尔值，在进行运算
	2、与运算中，如果两个值都为true，则返回后面的值
	如果两个值中有false，则返回前面的值
	var result=1&&2;	/result=2
	var result=2&&1;	/result=1
	====
	var result=0&&1;	/result=0
	var result=1&&NaN;	/result=1
	3、与运算中如果第一值为true，则返回第二个值
	如果第一个值为false，则返回第一个值，返回的均为原值，不是布尔值
#### 或运算
	如果第一个值为true，则返回第一个值
	如果第一个值为false，则返回第二个值
### 关系运算符
	1、数字情况：关系式成立返回true，否则返回false
	2、非数字情况是，现将其转换为数字 任何值和NaN比较都返回false
	3、比较两个字符串，比较其字符编码第一位，如果第一位相同，则比较下一位
	4、比较两个字符串型的数字时，一定要转型
#### Unicode编码
	在控制台输出Unicode编码对应的图形
	console.log("\u2680");	/十六进制编码
	在页面输出Unicode编码对应的图形
	<h1>&#9856;</h1>	/十进制编码
### 相等运算符
#### 相等
	1、用"=="进行运算时，先将其转换为相同的类型在进行比较
	cnosole.log(null==0);	/false
	2、undefined衍生为null
	console.log(undefined==null);/true
	3、NaN不和任何值相等，用isNaN()判断一个值是否为NaN
	4、全等(===) 不会进行强制类型转换，类型不同直接返回false
### 条件运算符
	var a=10;
	var b=20;
	var max=a>b?a:b;
### 循环
#### while循环 
	do...while比while多执行一次
#### for循环
	水仙花数
	var a,b,c;
	var i=0;
	for(a=0;a<10;a++){
		for(b=0;b<10;b++){
			for(c=0;c<10;c++){
				if(a*a*a+b*b*b+c*c*c==a*100+b*10+c){
					console.log(a+"+"+b+"+"+c+"="+(a*100+b*10+c));
				}
			}
		}
	}
#### 质数练习 10.16
	var i;
	var flag=1;
	var num=prompt("输入一个数字：");
	for(i=2;i<num;i++){
		if(num%i==0){
			flag=2;
		}
	}
	if(flag==1){
		alert("是质数")
	}else{
		alert("不是质数");
	}
#### break和continue
	break结束本次循环
	continue结束当前循环
### 对象
#### 自建对象
	var obj=new Object();
	obj.name="zhanghuan";	//添加属性
	delete obj.name; //删除属性
	==================
    属性名:
	使用[]操作属性更加灵活;
	obj["123"]=789;
	obj["456"]=891;
	var a ="123";	//变量a可以灵活变化
	console.log(obj[a]);
    属性值：
	属性值可以是其他对象
	var obj2=new Object();
	obj2.name="zhanghuan"
	obj.test=obj2;
	console.log(obj.test);
	==================
	in运算符---检查一个对象中是否有指定的属性
	有则返回true，没有则返回false
	console.log("test" in obj);	//true
#### 宿主对象
	目前来讲主要是浏览器提供的对象
	BOM DOM 
	比如：console.log() document.writer()
#### 内建对象
	ES标准中定义的对象，任何的ES都可以实现
	比如：Math String Number Boolean Function Object
### 基本数据类型和引用数据类型
	基本数据类型的值在栈内存中存储，变量之间互不影响
	引用数据类型的值在堆内存中存储，每个对象创建一个新的空间，栈内存中保存的是对象的地址
	===
	比较两个基本数据类型的数值时，比较的是数值
	比较两个引用数据类型时，比较的是其地址，地址不同返回false
###10.21
### 对象字面量
	var obj={};	//使用字面量创建对象
	语法：var obj2={name:"zhangsan",
			age:20,
			sex:"male"};
### 函数
	1、var fun=new Function();	//构造函数
	2、function fun(){
		};
	3、var fun=function(){		//匿名函数
		};
#### 函数参数
	function sun(a,b){
	consloe.log(a+b)
		}		//解析器不会检查实参类型
	sum(123,"hello");	//123hello
#### 返回值
	return 可以是任何值；
#### 实参可以是任何值
### 作用域
	1、全局作用域
	- 在页面打开时创建，页面关闭时销毁
	- 全局作用域有一个浏览器创建的对象window，可以直接使用，所创建的属性都会保存在window中
	- var a = 10;
	- function fun(){
		alert("");
		}
	- console.log(window.a);	//10
	- consloe.log(window.fun());
	==========
	变量声明提前：
	在js中，用var声明的变量，会在所有代码执行之前声明，但是不会赋值。
	2、局部作用域
	