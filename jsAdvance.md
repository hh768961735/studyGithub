#### 原型对象
	function Person(){	
	}
	Person.prototype.name="Bob";
	Person.prototype.age=10;
	Person.prototype.gender="male";
	Person.prototype.sayName=function(){
		console.log(this.name);
	}
	var person1=new Person();
	person1.name="John";
	person1.age=15;
	person1.sayName();	// John
	var person2=new Person();
	person2.sayName();	// Bob
	console.log(person1.__proto__);//隐式原型
	console.log(person1.prototype);//显式原型
	//用in检查对象中是否有某个属性是，无论实例中还是原型中有，都会返回true
	console.log("name" in person1);

	//hasOwnProperty检查实例还是原型中的属性
	console.log(person1.hasOwnProperty("age"));
	console.log(person1.__proto__.hasOwnProperty("hasOwnProperty"));

	//hasOwnPorperty方法在原型对象的原型中
	console.log(person1.__proto__.__proto__.hasOwnProperty("hasOwnProperty"));
	console.log(person1.__proto__.__proto__.__proto__);//null
	==========
	访问一个属性或者方法是，先在实例中寻找，有就使用，没有则在原型中找，有则使用，如果还没有就去原型的原型中寻找，知道找到object的原型，即没有原型，返回undefined
#### 原型链
	![原型链](https://github.com/hh768961735/h5Management/blob/master/img/prototype.png "url")
	<p><img src="https://github.com/hh768961735/h5Management/blob/master/img/prototype.png" alt="原型链" title="" /></p>
#### Ajax
##### XMLHttpRequest
	
	var ajax = new XMLHttpRequest();
		// 第二步： 设置状态监听函数
		ajax.onreadystatechange = function() {
			
		// 第五步：在监听函数中，判断readyState=4 && status=200表示请求成功
		if (ajax.readyState == 4 && ajax.status == 200) {
			// 第六步： 使用responseText、responseXML接受响应数据，并使用原生JS操作DOM进行显示
			console.log(ajax.responseText);
			console.log(ajax.responseXML); // 返回不是XML，显示null
			console.log(JSON.parse(ajax.responseText));
			console.log(eval("(" + ajax.responseText + ")"));
		}
	}
	// 第三步： open一个链接
	ajax.open("GET", "h51701.json", false); //true异步请求，false同步

	// 第四步： send一个请求。 可以发送对象和字符串，不需要传递数据发送null
##### jQuery
	$.ajax({
		url: url,
		method: "GET",
		contentType:  "application/x-www-form-urlencoded",
		context: Object,
		async: true/false,
		dataType: "JSON",
		data:{
		},
		success: function (data) {
			},
			error{
				
			}	  
	})
#### 回调函数
	//定义了但是没有调用也可以执行
	//DOM对象
	document.getElementById("app").onclick = function(){
	 	alert(this.innerHTML);
	 };
	 //定时器
	 setTimeout(function(){
	 	alert(1);
	 },2000)
	 //匿名函数自调用 IIFES
	 (function (){
	 	var a = 1;
	 	function test(){
	 		console.log(++a); 
	 	}
	 	window.$ = function(){
	 		return {
	 			test: test
	 		}
	 	}
	 })()
	 $().test();
#### this
		//this指向当前调用的对象
		function Person(person){
		console.log(this);
		this.person = person;
		this.getPerson = function(){
			console.log(this); //Person
			return this.person;
		};
		this.setPerson = function(){
			console.log(this); //obj 
			return this.person;
		}
	}
	Person("hh"); //window.Person
	var p = new Person();
	p.getPerson("hh");
	var obj = {};
	p.setPerson.call(obj,"jj");
#### that
		// 把当前的this对象赋值给that，则即使this改变，that依然指向之前的那个对象
		function s(){
			this.a = 1;
			console.log(a);
		}
		function b(){
			var that = this;
			console.log(that.a);
		}
		s();
		b();
		
#### 关于this的误解
##### 1、this引用function本身
		function fn(num) {
		     console.log( "fn: " + num );
		     // count用于记录fn的被调用次数
		     this.count++;
		 }
		 fn.count = 0;
		 var i;
		 for (i=0; i<10; i++) {
		     if (i > 5) {
		         fn( i );
		     }
		 }
		 // fn: 6
		 // fn: 7
		 // fn: 8
		 // fn: 9
		  
		 console.log( fn.count ); // 0 
		count自增隐式的创建了一个全局变量，初始值为undefined，打印输出为NaN,
		每次自增依然是NaN,fu.count并没有传值到fn方法，fn.count一直为0，所以
		this引用的是function这种理解是错误的
##### 2、this引用的是function的词法作用域
		function fn1() {
		    var a = 2;
		    this.fn2();//以为this引用的是fn1的词法作用域
		}
		function fn2() {
		    console.log( this.a );
		}
		fn1(); //ReferenceError