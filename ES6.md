#### ES6新特性
###  const与let
	function getClothing(isCold) {
 		 if (isCold) {
    			var freezing = 'Grab a jacket!';
  		} else {
   		 	var hot = 'It's a shorts kind of day.';
   			console.log(freezing);
  		}
	}
	getClothing(false);  
	输出undefine,var声明的变量被声明提前
	freezing被声明，但是没有赋值，所以输出undefined,这是var的缺点。
	// 由const和let声明的变量不会声明提前,直接报错
	// let可以不初始化,声明之后直接赋值即可,不能再次声明(同一作用域下)
	// const必须初始化,同一作用域内不可重新声明且赋值
	function getClothing(isCold) {
 		 if (isCold) {
    			const freezing = 'Grab a jacket!';
  		} else {
   		 	const hot = 'It's a shorts kind of day.';
   			console.log(freezing);
  		}
	}
	运行getClothing(false),控制台报错，因为freezing不在else作用域中，
	没有被声明，const和let不会被声明提前。
	+ let声明变量可以重新赋值，但是不能再同一作用域内重新声明(不用声明，直接赋值)
	+ const声明的变量必须初始化，不能再同一作用域内声明且重新赋值
### class
#### 定义类
	class Rectangle {
		constructor(height,width){
			this.height = height;
			this.width = width;
		}
	}
#### 声明提升
	类声明不会提前，需要先声明类，在进行实例化操作。
	let p = new Rectangle(); 
	// ReferenceError
	
	class Rectangle {}
### 类表达式
	<!-- 匿名类 -->
	let Rectangle = class{};
	<!-- 命名类 -->
	let Rectangel = class Rectangle{}
### 类体方法和定义
#### 严格模式(use strict)
	类声明和类表达式的主体都执行在严格模式下。比如，构造函数，静态方法，原型方法，getter和setter都在严格模式下执行。
#### 构造函数
	constructor方法，用于创建和初始化一个由class创建的对象。一个类只能有一个constructor方法。
	一个构造函数可以使用 super 关键字来调用一个父类的构造函数。
#### 原型方法
	class Rectangle {
	    // constructor
	    constructor(height, width) {
	        this.height = height;
	        this.width = width;
	    }
	    // Getter
	    get area() {
	        return this.calcArea()
	    }
	    // Method
	    calcArea() {
	        return this.height * this.width;
	    }
	}
	const square = new Rectangle(10, 10);
	
	console.log(square.area);
	// 100
#### 静态方法
	<!-- 静态方法可以直接通过类名调用，不需要实例化类，通常用于为一个应用程序创建工具函数 -->
	class Point {
	    constructor(x, y) {
	        this.x = x;
	        this.y = y;
	    }
	
	    static distance(a, b) {
	        const dx = a.x - b.x;
	        const dy = a.y - b.y;
	
	        return Math.hypot(dx, dy);
	    }
	}
	
	const p1 = new Point(5, 5);
	const p2 = new Point(10, 10);
	
	console.log(Point.distance(p1, p2));
	haha

	