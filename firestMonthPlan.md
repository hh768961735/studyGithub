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

#### 函数中的prototype

##### 原型（对象属性）
        - Javascript规定，每一个函数都有一个prototype对象属性，指向另一个对象（原型链上面的）。

        - prototype(对象属性)的所有属性和方法，都会被构造函数的实例继承。这意味着，我们可以把那些不变(公用)的属性和方法，直接定义在prototype对象属性上。

        - prototype就是调用构造函数所创建的那个实例对象的原型（proto）。

        - prototype可以让所有对象实例共享它所包含的属性和方法。也就是说，不必在构造函数中定义对象信息，而是可以直接将这些信息添加到原型中。

##### 原型链 （JS原型与原型链继承）
        - 实例对象与原型之间的连接，叫做原型链。proto( 隐式连接 )

        - JS在创建对象的时候，都有一个叫做proto的内置属性，用于指向创建它的函数对象的原型对象prototype。

        - 内部原型(proto)和构造器的原型（prototype）
        - 每个对象都有一个proto属性,原型链上的对象正是依靠这个属性连结在一起
        - 作为一个对象，当你访问其中的一个属性或方法的时候，如果这个对象中没有这个方法或属性，那么Javascript引擎将会访问这个对象的proto属性所指向上一个对象，
        并在那个对象中查找指定的方法或属性，如果不能找到，那就会继续通过那个对象的proto属性指向的对象进行向上查找，直到这个链表结束。

        - 每一个函数都有一个原型属性prototype(对象属性)，里面放置的是共有、公有的属性或者方法。(一般情况属性是私有的)。注意，只有函数才有prototyoe属性，

            function Person() {
       
            }
            var p = new Person()
            console.log(Person.prototype); // Object{} 
            console.log(p.prototype); //undefined
##### 浅谈constructor

        - 在 Javascript 语言中，constructor 属性是专门为 function 而设计的，它存在于每一个 function 的prototype 属性中。这个 constructor 保存了指向 function 的一个引用。
            function Person() {
       
            }
            var p = new Person()
            console.log(Person.prototype); // Object{} 
            console.log(p.prototype); // undifined
            console.log(p.constructor); //function Person(){}    
            此处的p是通过 Person函数构造出来的，所以p的constructor属性指向Person
            console.log(Person.constructor); //function Function(){}
            之前提过，每个函数其实是通过new Function（）构造的
            console.log({}.constructor); // function Object(){}
            每个对象都是通过new Object（）构造的
            console.log(Object.constructor); // function Function() {}
            Object也是一个函数，它是Function（）构造的
            console.log([].constructor);  //function Array(){}

                function Person(name,age){
                    this.name = name;
                    this.age = age;
                    this.sayHello = function(){
                        console.log(this.name + "say hello");
                    }
                }
                var girl = new Person("bella",23);
                var boy = new Person("alex",23);
                console.log(girl.name);  //bella
                console.log(boy.name);   //alex
                console.log(girl.sayHello === boy.sayHello);  //false

                    function Person(name,age){
                        this.name = name;
                        this.age = age;
                        
                    }
                    Person.prototype.sayHello=function(){
                        console.log(this.name + "say hello");
                    }
                    var girl = new Person("bella",23);
                    var boy = new Person("alex",23);
                    console.log(girl.name);  //bella
                    console.log(boy.name);   //alex
                    console.log(girl.sayHello === boy.sayHello);  //true          

##### JS 在创建对象（不论是普通对象还是函数对象）的时候，都有一个叫做 __proto__ 的内置属性，用于指向创建它的构造函数的原型对象。

        -   var obj = []
            console.log(obj.__proto__ === Array.prototype)//true

#### 显示原型与隐式原型

        在js中万物皆对象，方法(Function)是对象，方法的原型（Function.prototype）是对象，对象具有属性（__proto__）称为隐式原型，对象的隐式原型指向构造该对象的构造函数的显式原型。

        方法(Function)是一个特殊的对象，除了和其他对象一样具有__proto__属性以外，它还有一个自己特有的原型属性(prototype)，这个属性是一个指针，指向原型对象。原型对象也有一个属性叫constructor，这个属性包含一个指针，指向原构造函数。

        注意：通过Function.prototype.bind方法构造出来的函数没有prototype属性。

        注意：Object.prototype.这个对象的是个例外，它的__proto__值为null。      

        https://upload-images.jianshu.io/upload_images/2404178-70684ddd20c13efb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240&_=6014925

#### instanceof

        - instanceof运算符用来判断一个构造函数的prototype属性所指向的对象是否存在另外一个要检测对象的原型链上

        function Person(){

        };
        var p =new Person();
        console.log(p instanceof Person);//true

        function Person() {}
        console.log(Object instanceof Object);     //true
        //第一个Object的原型链：Object=>
        //Object.__proto__ => Function.prototype=>Function.prototype.__proto__=>Object.prototype
        //第二个Object的原型：Object=> Object.prototype

        console.log(Function instanceof Function); //true
        //第一个Function的原型链：Function=>Function.__proto__ => Function.prototype
        //第二个Function的原型：Function=>Function.prototype

        console.log(Function instanceof Object);   //true
        //Function=>
        //Function.__proto__=>Function.prototype=>Function.prototype.__proto__=>Object.prototype
        //Object => Object.prototype

        console.log(Person instanceof Function);      //true
        //Person=>Person.__proto__=>Function.prototype
        //Function=>Function.prototype

        console.log(String instanceof String);   //false
        //第一个String的原型链：String=>
        //String.__proto__=>Function.prototype=>Function.prototype.__proto__=>Object.prototype
        //第二个String的原型链：String=>String.prototype

        console.log(Boolean instanceof Boolean); //false
        //第一个Boolean的原型链：Boolean=>
        //Boolean.__proto__=>Function.prototype=>Function.prototype.__proto__=>Object.prototype
        //第二个Boolean的原型链：Boolean=>Boolean.prototype

        console.log(Person instanceof Person); //false
        //第一个Person的原型链：Person=>
        //Person.__proto__=>Function.prototype=>Function.prototype.__proto__=>Object.prototype
        //第二个Person的原型链：Person=>Person.prototype

#### 执行上下文

    1.单线程，在主进程上运行

　　2.同步执行，从上往下按顺序执行

　　3.全局上下文只有一个，浏览器关闭时会被弹出栈

　　4.函数的执行上下文没有数目限制

　　5.函数每被调用一次，都会产生一个新的执行上下文环境

#### 执行上下文栈
    执行全局代码时，会产生一个执行上下文环境，每次调用函数都又会产生执行上下文环境。当函数调用完成时，这个上下文环境以及其中的数据都会被消除，
    
    再重新回到全局上下文环境。处于活动状态的执行上下文环境只有一个。

　　其实这是一个压栈出栈的过程。

    https://upload-images.jianshu.io/upload_images/4067575-42d6c06ba1f19f3e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240

    执行上下文共分3个阶段，分别是：
　　　　1.创建阶段

　　　　　　(1).生成变量对象

　　　　　　(2).建立作用域链

　　　　　　(3).确定 this 指向

 
　　　　2.执行阶段

　　　　　　(1).变量赋值

　　　　　　(2).函数引用

　　　　　　(3).执行其他代码

 
　　　　3.销毁阶段

　　　　　　执行完毕出栈，等待回收被销毁

#### 作用域与作用域链
		作用域是可访问变量的集合。
##### JavaScript 作用域
   + 在 JavaScript 中, 对象和函数同样也是变量。
   
   + 在 JavaScript 中, 作用域为可访问变量，对象，函数的集合。

   + JavaScript 函数作用域: 作用域在函数内修改。 
   
##### JavaScript 局部作用域
		
   + 变量在函数内声明，变量为局部作用域。

   + 局部变量：只能在函数内部访问。

	// 此处不能调用 carName 变量
	function myFunction() {
		var carName = "Volvo";
		// 函数内可调用 carName 变量
	}
	
	因为局部变量只作用于函数内，所以不同的函数可以使用相同名称的变量。
	局部变量在函数开始执行时创建，函数执行完后局部变量会自动销毁。
	
##### JavaScript 全局变量
	变量在函数外定义，即为全局变量。
	
	全局变量有 全局作用域: 网页中所有脚本和函数均可使用。 
	
	var carName = " Volvo";
	 
	// 此处可调用 carName 变量
	function myFunction() {
	    // 函数内可调用 carName 变量
	}
	
##### JavaScript 变量生命周期
	JavaScript 变量生命周期在它声明时初始化。
	
	局部变量在函数执行完毕后销毁。
	
	全局变量在页面关闭后销毁。
	
#### 作用域链
	通俗地讲，当声明一个函数时，局部作用域一级一级向上包起来，就是作用域链。
	
	1.当执行函数时，总是先从函数内部找寻局部变量
	
	2.如果内部找不到（函数的局部作用域没有），则会向创建函数的作用域（声明函数的作用域）寻找，依次向上
	
   ![](新建文本文档 (2)_files/2.jpg)
   
   当执行fn1时，创建函数fn1的执行环境，并将该对象置于链表开头，然后将函数fn的调用对象放在第二位，最后是全局对象，作用域链的链表的结构是fn1->fn->window。从链表的开头寻找变量a，即fn1函数内部找变量a，找到了，结果是20。
   
   同样，执行fn2时，作用域链的链表的结构是fn2->fn->window。从链表的开头寻找变量a，即fn2函数内部找变量a，找不到，于是从fn内部找变量a，找到了，结果是10。
   
   最后在最外层打印出变量a，直接从变量a的作用域即全局作用域内寻找，结果为1。
   
 #### 闭包
	JavaScript 变量可以是局部变量或全局变量。
	
	私有变量可以用到闭包。
	
##### 全局变量
	函数可以访问由函数内部定义的变量，如：

	function myFunction() {
	    var a = 4;
	    return a * a;
	}
	
	函数也可以访问函数外部定义的变量，如：
	
	var a = 4;
	function myFunction() {
	    return a * a;
	}
	
	后面一个实例中， a 是一个全局变量。
	
	在web页面中全局变量属于window对象。
	
	全局变量可应用于页面上的所有脚本。
	
	在第一个实例中， a 是一个 局部 变量。
	
	局部变量只能用于定义它函数内部。对于其他的函数或脚本代码是不可用的。
	
	全局和局部变量即便名称相同，它们也是两个不同的变量。修改其中一个，不会影响另一个的值。
	
	变量声明时如果不使用 var 关键字，那么它就是一个全局变量，即便它在函数内定义。
	
##### JavaScript 内嵌函数
	所有函数都能访问全局变量。  
	
	实际上，在 JavaScript 中，所有函数都能访问它们上一层的作用域。
	
	JavaScript 支持嵌套函数。嵌套函数可以访问上一层的函数变量。
	
	该实例中，内嵌函数 plus() 可以访问父函数的 counter 变量：
	
	function add() {
	    var counter = 0;
	    function plus() {
			counter += 1;
		}
	    plus();    
	    return counter; 
	}
	
##### JavaScript 闭包
	var add = (function () {
	    var counter = 0;
	    return function () {
			return counter += 1;
		}
	})();
	 
	add();
	add();
	add();
	
	变量 add 指定了函数自我调用的返回字值。
	
	自我调用函数只执行一次。设置计数器为 0。并返回函数表达式。
	
	add变量可以作为一个函数使用。非常棒的部分是它可以访问函数上一层作用域的计数器。
	
	这个叫作 JavaScript 闭包。它使得函数拥有私有变量变成可能。
	
	计数器受匿名函数的作用域保护，只能通过 add 方法修改。
	
##### 闭包原理
	闭包的实现原理，其实是利用了作用域链的特性，我们都知道作用域链就是在当前执行环境下访问某个变量时，
	如果不存在就一直向外层寻找，最终寻找到最外层也就是全局作用域，这样就形成了一个链条。
	
	例如：
	var age = 18;
	function cat(){
	    age++;
	    console.log(age);// cat函数内输出age，该作用域没有，则向外层寻找，结果找到了，输出[19];
	}
	cat();//19
	
	如果程序还有其他函数，也需要用到age的值，则会受到影响，而且全局变量还容易被人修改，比较不安全，
	这就是全局变量容易污染的原因，所以我们必须解决变量污染问题，那就是把变量封装到函数内，让它成为局部变量。
	
	function person(){
	    var age = 18;
	    function cat(){
	        age++;
	        console.log(age);
	    }
	    return cat;
	}
	var per = person();//per相当于函数cat
	per();// 19 即cat() 这样每次调用不在经过age的初始值，这样就可以一直增加了
	per();// 20
	per();// 21
	
##### 闭包的作用
	作用1：隐藏变量，避免全局污染
	
	作用2：可以读取函数内部的变量
	
	同时闭包使用不当，优点就变成了缺点：
	
	缺点1：导致变量不会被垃圾回收机制回收，造成内存消耗
	
	缺点2：不恰当的使用闭包可能会造成内存泄漏的问题
	
	为什么使用闭包时变量不会被垃圾回收机制收销毁呢，这里需要了解一下JS垃圾回收机制；
	
	JS规定在一个函数作用域内，程序执行完以后变量就会被销毁，这样可节省内存；
	
	使用闭包时，按照作用域链的特点，闭包（函数）外面的变量不会被销毁，因为函数会一直被调用，所以一直存在，如果闭包使用过多会造成内存销毁。


        



