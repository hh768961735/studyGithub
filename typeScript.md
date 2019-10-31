### 元组
	元组类型允许表示一个已知元素数量和类型的数组，各元素的类型不必相同。 
	比如，你可以定义一对值分别为 string和number类型的元组。
	let x: [string, number];
	x = ['hello',10];
	console.log(x[0].substr(1)); //ok
	console.log(x[1].substr(1)); // Error, 'number' does not have 'substr'
### 布尔值
	let isDone: boolean = false;
### 数字
	let decLiteral: number = 6;
	let hexLiteral: number = 0xf00d;
	let binaryLiteral: number = 0b1010;
	let octalLiteral: number = 0o744;
### 字符串
	let name: string = "bob";
	name = "smith";
#### 模板字符串
	反引号 ` `
	let name: string = `Gene`;
	let age: number = 37;
	let sentence: string = `Hello, my name is ${ name }.
	I'll be ${ age + 1 } years old next month.`;
### 数组
	let arr: array[] = [1,2,3];
	let list: Array<number> = [1, 2, 3];
### 枚举
	enum Color {Red, Green, Blue}
	let color = Color.Green;
	
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
### Void
	只能赋值undefined和null
	let unusable: void = undefined;
### Never
	never类型表示的是那些永不存在的值的类型。 例如， never类型是那
	些总是会抛出异常或根本就不会有返回值的函数表达式或箭头函数表达式
	的返回值类型； 变量也可能是 never类型，当它们被永不为真的类型保
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
### Object
	