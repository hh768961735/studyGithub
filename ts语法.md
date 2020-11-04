## 基础类型
### 布尔值
	let isDone: boolean = false;
### 数字
	let decLiteral: number = 6;
	let hexLiteral: number = 0xf00d; //十六进制
	let binaryLiteral: number = 0b1010; //二进制
	let octalLiteral: number = 0o744; //八进制
### 字符串
	let name: string = "bob";
	name = "smith";
### 模板字符串
	反引号 ` `
	let name: string = `Gene`;
	let age: number = 37;
	let sentence: string = `Hello, my name is ${ name }.
	I'll be ${ age + 1 } years old next month.`;
### 数组
	let arr: array[] = [1,2,3];
	数组泛型，Array<元素类型>：
	let list: Array<number> = [1, 2, 3];
### 元组
	元组类型允许表示一个已知元素数量和类型的数组，各元素的类型不必相同。 
	比如，你可以定义一对值分别为 string和number类型的元组。
	let x: [string, number];
	x = ['hello',10];
	console.log(x[0].substr(1)); //ok
	console.log(x[1].substr(1)); // Error, 'number' does not have 'substr'
### 枚举
	enum类型是对JavaScript标准数据类型的一个补充。 像C#等其它语言一样，使用枚举类型可以为一组数值赋予友好的名字。
	
	enum Color {Red, Green, Blue}
	let c: Color = Color.Green;
	
	enum Color {Red = 1, Green = 2, Blue = 3}
	let c: Color = Color.Green;
	console.log(Color[2]);
### Any
	有时候，我们会想要为那些在编程阶段还不清楚类型的变量指定一个类型。 
	这些值可能来自于动态的内容，比如来自用户输入或第三方代码库。这种
	情况下，我们不希望类型检查器对这些值进行检查而是直接让它们通过编
	译阶段的检查。那么我们可以使用 any类型来标记这些变量：
	let notSure: any = 4;
	notSure = "maybe a string instead";
	notSure = false; // okay, definitely a boolean
	当你只知道一部分数据的类型时，any类型也是有用的。 比如，你有一个数组，它包含了不同的类型的数据：
	
	let list: any[] = [1, true, "free"];
	
	list[1] = 100;
### Void
	当一个函数没有返回值时，你通常会见到其返回值类型是 void
	只能赋值undefined和null
	let unusable: void = undefined;
### Never
	never类型表示的是那些永不存在的值的类型。例如，never类型是那
	些总是会抛出异常或根本就不会有返回值的函数表达式或箭头函数表达式
	的返回值类型；变量也可能是never类型，当它们被永不为真的类型保
	护所约束时。
	never类型是任何类型的子类型，也可以赋值给任何类型；然而，没有类
	型是never的子类型或可以赋值给never类型（除了never本身之外）。 
	即使 any也不可以赋值给never。
	
	// 返回never的函数必须存在无法达到的终点
	function error(message: string): never {
	    throw new Error(message);
	}
	
	// 推断的返回值类型为never
	function fail() {
	    return error("Something failed");
	}
	
	// 返回never的函数必须存在无法达到的终点
	function infiniteLoop(): never {
	    while (true) {
	    }
	}
### null和undefined
	默认情况下null和undefined是所有类型的子类型。 就是说你可以把 null和undefined赋值给number类型的变量。
## 变量声明
### var 声明
	一直以来我们都是通过var关键字定义JavaScript变量。

	for (var i = 0; i < 10; i++) {
		setTimeout(function() { console.log(i); }, 100 * i);
	}
	
### let 声明
#### 块作用域
	 当用let声明一个变量，它使用的是词法作用域或块作用域。不同于使用 var声明的变量那样可以在包含它们的函
	 数外访问，块作用域变量在包含它们的块或for循环之外是不能访问的。
	 
	 function f(input: boolean) {
	     let a = 100;
	
	     if (input) {
	         // Still okay to reference 'a'
	         let b = a + 1;
	         return b;
	     }
	 
	     // Error: 'b' doesn't exist here
	     return b;
	 }
	 
	 这里我们定义了2个变量a和b。a的作用域是f函数体内，而b的作用域是if语句块里。
### const声明
	const 声明是声明变量的另一种方式。

	它们与let声明相似，但是就像它的名字所表达的，它们被赋值后不能再改变。 
	换句话说，它们拥有与 let相同的作用域规则，但是不能对它们重新赋值。
	
	const numLivesForCat = 9;
	const kitty = {
	    name: "Aurora",
	    numLives: numLivesForCat,
	}
	
	// Error
	kitty = {
	    name: "Danielle",
	    numLives: numLivesForCat
	};
	
	// all "okay"
	kitty.name = "Rory";
	kitty.name = "Kitty";
	kitty.name = "Cat";
	kitty.numLives--;
	
	除非你使用特殊的方法去避免，实际上const变量的内部状态是可修改的。 
