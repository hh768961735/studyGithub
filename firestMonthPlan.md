#### 数据变量_内存 2020/01/05
##### 什么是数据
		
		- 存储在内存中的一种代表特殊信息的概念。
		- 数据可传递，可运算，可赋值
		
##### 什么是内存
		内存条通电之后产生可存储的空间就是内存，通电产生，断点消失。
		内存分类：
		
			- 堆：基本数据类型
			- 栈：引用数据类型
		
##### 什么是变量
		变量是可变化的值量，包括变量名和变量值；
		每个变量占用一部分内存，通过变量名查找到内存中的变量值，也就是内存中数据
##### 数据、内存、变量之间的关系
		数据在内存中存储，变量是内存的标识

#### js对象 2020/01/12
##### 什么是对象
		存储数据的容器	
		var person = {
			name: "Bob",
			age: "20",
			setName: function(name){
				this.name = name;
			}
			setAge: function(age){
				this.age = age;
			}
		}
		
		person.setName('Tom');
		person['setAge']('10');
##### 使用[]需要注意：
			1、变量名包含特殊字符
			2、变量名不确定
##### 关于变量赋值问题
###### 两个引用对象指向同一个对象,通过一个变量修改对象内部数据，另一个变量指向的对象会被修改
		var a = {
			name: 'Tom'
		};
		var b = a;
		b.age = '10';
		console.log(a.age);//10
##### 两个引用对象指向同一个对象，其中一个引用变量指向另一个对象, 另一个变量指向的对象不会被修改
		var a = {
			name: 'Tom'
		};
		var b = a;
		a = {
			name: 'Bob'
		}
		console.log(b.name);//Tom

#### 函数 2021/01/16
##### 什么是函数
        - 函数是被设计为执行特定任务的代码块。

        - 函数会在某代码调用它时被执行。
##### 函数表达式
        - 函数可以通过一个表达式定义。

        - 函数表达式可以存储在变量中：
            var x = function (a, b) {
                return a * b
                };
##### Function() 构造函数
        - 函数同样可以通过内置的 JavaScript 函数构造器（Function()）定义。
            var myFunction = new Function("a", "b", "return a * b");
            var x = myFunction(4, 3);

##### 函数提升（Hoisting）
        - 提升（Hoisting）是 JavaScript 默认将当前作用域提升到前面去的的行为。

        - 提升（Hoisting）应用在变量的声明与函数的声明。

        - 因此，函数可以在声明之前调用：
            myFunction(5);

            function myFunction(y) {
                return y * y;
            }
##### 自调用函数
        - 函数表达式可以 "自调用"。

        - 自调用表达式会自动调用。

        - 如果表达式后面紧跟 () ，则会自动调用。

        - 不能自调用声明的函数。

        - 通过添加括号，来说明它是一个函数表达式：

        (function () {
            var x = "Hello!!";      // 我将调用自己
        })();

##### 函数是对象
        - 在 JavaScript 中使用 typeof 操作符判断函数类型将返回 "function" 。

        - 但是JavaScript 函数描述为一个对象更加准确。

        - JavaScript 函数有 属性 和 方法。

        - arguments.length 属性返回函数调用过程接收到的参数个数

        function myFunction(a, b) {
            return arguments.length;
        }

##### 箭头函数
        - ES6 新增了箭头函数。

        - 箭头函数表达式的语法比普通函数表达式更简洁。

        // ES5
        var x = function(x, y) {
            return x * y;
        }
 
        // ES6
        const x = (x, y) => x * y;

#### 回调函数 2021/01/16
##### 什么是回调函数
        - 一个函数被作为参数传递给另一个函数（在这里我们把另一个函数叫做“otherFunction”），回调函数在otherFunction中被调用。

        //它就是回调函数
        $("#btn_1").click(function() {
            alert("Btn 1 Clicked");
        });  
        //或者
        function click() { // 它就是回调函数
            alert("Btn 1 Clicked");
        }
        $("#btn_1").click(click);  
##### 回调函数是怎样运作的
        - 因为函数在Javascript中是第一类对象，我们像对待对象一样对待函数，因此我们能像传递变量一样传递函数，在函数中返回函数，
        - 在其他函数中使用函数。当我们将一个回调函数作为参数传递给另一个函数是，我们仅仅传递了函数定义。我们并没有在参数中执行函数。
        - 我们并不传递像我们平时执行函数一样带有一对执行小括号()的函数。

        //第一种方法：匿名函数作为回调函数
            var generalLastName = "Cliton";
            function getInput(options, callback){
                var arr = [];
                arr.push(options);
                //将全局变量generalLastName传递给回调函数
                callback(generalLastName,arr);
            }
            getInput({name:"Rich",speciality:"Javascript"}, function(generalLastName,arr){
                console.log(generalLastName + ":" + arr[0].speciality) // Cliton:Javascript
            });

            //第二种方法：命名函数作为回调函数
            var generalLastName = "Cliton";
            function getInput(options, callback){
                var arr = [];
                arr.push(options);
                //将全局变量generalLastName传递给回调函数
                callback(generalLastName,arr);
            }
            function call(generalLastName,arr){
                console.log(generalLastName + ":" + arr[0].speciality) // Cliton:Javascript
            }
            getInput({name:"Rich",speciality:"Javascript"}, call);

##### JavaScript this 关键字 2021/01/17
    面向对象语言中 this 表示当前对象的一个引用。

    但在 JavaScript 中 this 不是固定不变的，它会随着执行环境的改变而改变。

    - 在方法中，this 表示该方法所属的对象。
    - 如果单独使用，this 表示全局对象。
    - 在函数中，this 表示全局对象。
    - 在函数中，在严格模式下，this 是未定义的(undefined)。
    - 在事件中，this 表示接收事件的元素。
    - 类似 call() 和 apply() 方法可以将 this 引用到任何对象。
##### 方法中的 this
    - 在对象方法中， this 指向调用它所在方法的对象。

    - fullName 方法所属的对象就是 person。   

    var person = {
        firstName: "John",
        lastName : "Doe",
        id       : 5566,
        fullName : function() {
                return this.firstName + " " + this.lastName;
            }
        };      
##### 单独使用 this
        - 单独使用 this，则它指向全局(Global)对象。

        - 在浏览器中，window 就是该全局对象为 [object Window]:

        var x = this;
##### 函数中使用 this（默认）
        - 在函数中，函数的所属者默认绑定到 this 上。

        function myFunction() {
            return this;
        }

##### 函数中使用 this（严格模式）
        - 严格模式下函数是没有绑定到 this 上，这时候 this 是 undefined。

        "use strict";
        function myFunction() {
            return this;
        }

##### 显式函数绑定
        - 在 JavaScript 中函数也是对象，对象则有方法，apply 和 call 就是函数对象的方法。这两个方法异常强大，他们允许切换函数执行的上下文环境（context），即 this 绑定的对象。

        - 在下面实例中，当我们使用 person2 作为参数来调用 person1.fullName 方法时, this 将指向 person2, 即便它是 person1 的方法：

        var person1 = {
            firstName: "Bob",
            fullName: function () {
                console.log(this.firstName + " " + this.lastName);
            }
        }
        var person2 = {
            firstName: "John",
            lastName: "Doe",
        }
        person1.fullName.call(person2); // 返回 "John Doe"


