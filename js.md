### 10.10
#### ������������
	String,Number,Null,undefined,Boolean���л����������� Objectһ�������������� 
#### ת���ַ� "\"
 	alert("hello world!");
	\" ��ʾ "
	\n ����
	\t �Ʊ��
	alert("\\");
	\\ ���һ��\
### 10.11
#### ��ʶ��
	1����ʶ���������֡���ĸ��_��$
	2�����������ֿ�ͷ
	3�������ǹؼ��ֺͱ�����
	4��һ�����շ�������
#### Number
	1.7976931348623157e+308  Number.MAX_VALUE	
	5e-324 			 Number.MIN_VALUE 
	���numberֵ���������ֵ ��᷵��Infinity ��ʾ������
	Infinity��NaN��typeof������������Number
#### Null
	ʹ��typeof���nullֵ����object
	ʹ��typeof���undefined����undefined
#### ǿ������ת��
	1������Number��Boolean���Ե���toString()
	null��undefinedû��toString()
	���ǿ�����String()����ֱ��ת��Ϊ�ַ���
	2���ַ���ת��Ϊ����
	(1) �ַ�����ֻ����������ֱ��ת��Ϊ����
	(2) �ַ����к��з�������ת��ΪNaN
	(3) �ַ���Ϊ����ת��Ϊ0
	3������ֵת��Ϊ����
	true->1
	false->0
	4��Nullת��Ϊ����
	null->0
	5��undefinedת��Ϊ����
	undefined->NaN
#### �������ֺ���ĸ���ַ���
	var a="123px";
	a=parseInt(a); //123
	var a="123.456px";
	a=parseFloat(a);//123.456
	====����Է�Stringʹ��parseInt()��parseFloat()	
	����ת��ΪStringȻ���ڲ���
	var a=true;
	a=parerInt(a);//NaN
#### ��������ֵ����ת��Ϊ����ֵ
	1����������ת��Ϊ����ֵ
	����0��NaN����false����������true
	2���ַ���ת��Ϊ����ֵ
	����Ϊ�գ�������Ϊtrue
	3��null��undefined����ת��Ϊfalse
	4��objectת��Ϊtrue
### �����
#### ���������
	�ӷ�����
	1���Է�Numberֵ��������ʱ���Ƚ���ת��ΪNumber�ڽ��м���
	2���κ�����NaN���㶼��NaN
	3�������ַ�����ӣ������ַ���ƴ��
	4���κ�ֵ���ַ�����ӣ���ת��Ϊ�ַ������ڽ���ƴ��
	5������Ϊ������������ͼ�һ�����ַ���""����ת��Ϊ	String����
	=====
	�κ�ֵ����- * /����ʱ������ת��ΪNumber
	����ͨ��-0��*1��/1������ֵת��ΪNumber
#### һԪ�����
	���Զ���������ʹ��+������ת��ΪNumber
#### ����
	var a=1;
	a++; ��ԭֵ���
	++a; ���������Ժ��ֵ
#### �Լ�
	a--; ��ԭֵ���
	--a; �����Լ����ֵ
### �߼������  &&��||��!
#### ������
	1���Բ���ֵ���з����㣬false��Ϊtrue��true��Ϊfalse
	2���Էǲ���ֵ�������㣬�Ƚ���ת��Ϊ����ֵ�ڽ�������
	3����������������ͽ������η����㼴��ת��Ϊ����ֵ
#### ������
	��false�ͷ���false
#### ������
	��true�ͷ���true
### �ǲ���ֵ���߼�����
#### ������
	1�����ڷǲ���ֵ���߼����㣬�Ƚ���ת��Ϊ����ֵ���ڽ�������
	2���������У��������ֵ��Ϊtrue���򷵻غ����ֵ
	�������ֵ����false���򷵻�ǰ���ֵ
	var result=1&&2;	/result=2
	var result=2&&1;	/result=1
	====
	var result=0&&1;	/result=0
	var result=1&&NaN;	/result=NaN
	3���������������һֵΪtrue���򷵻صڶ���ֵ
	�����һ��ֵΪfalse���򷵻ص�һ��ֵ�����صľ�Ϊԭֵ�����ǲ���ֵ
#### ������
	�����һ��ֵΪtrue���򷵻ص�һ��ֵ
	�����һ��ֵΪfalse���򷵻صڶ���ֵ
### ��ϵ�����
	1�������������ϵʽ��������true�����򷵻�false
	2������������ǣ��ֽ���ת��Ϊ���� �κ�ֵ��NaN�Ƚ϶�����false
	3���Ƚ������ַ������Ƚ����ַ������һλ�������һλ��ͬ����Ƚ���һλ
	4���Ƚ������ַ����͵�����ʱ��һ��Ҫת��
#### Unicode����
	�ڿ���̨���Unicode�����Ӧ��ͼ��
	console.log("\u2680");	/ʮ�����Ʊ���
	��ҳ�����Unicode�����Ӧ��ͼ��
	<h1>&#9856;</h1>	/ʮ���Ʊ���
### ��������
#### ���
	1����"=="��������ʱ���Ƚ���ת��Ϊ��ͬ�������ڽ��бȽ�
	cnosole.log(null==0);	/false
	2��undefined����Ϊnull
	console.log(undefined==null);/true
	3��NaN�����κ�ֵ��ȣ���isNaN()�ж�һ��ֵ�Ƿ�ΪNaN
	4��ȫ��(===) �������ǿ������ת�������Ͳ�ֱͬ�ӷ���false
### ���������
	var a=10;
	var b=20;
	var max=a>b?a:b;
### ѭ��
#### whileѭ�� 
	do...while��while��ִ��һ��
#### forѭ��
	ˮ�ɻ���
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
#### ������ϰ 10.16
	var i;
	var flag=1;
	var num=prompt("����һ�����֣�");
	for(i=2;i<num;i++){
		if(num%i==0){
			flag=2;
		}
	}
	if(flag==1){
		alert("������")
	}else{
		alert("��������");
	}
#### break��continue
	break��������ѭ��
	continue������ǰѭ��
### ����
#### �Խ�����
	var obj=new Object();
	obj.name="zhanghuan";	//�������
	delete obj.name; //ɾ������
	==================
    ������:
	ʹ��[]�������Ը������;
	obj["123"]=789;
	obj["456"]=891;
	var a ="123";	//����a�������仯
	console.log(obj[a]);
    ����ֵ��
	����ֵ��������������
	var obj2=new Object();
	obj2.name="zhanghuan"
	obj.test=obj2;
	console.log(obj.test);
	==================
	in�����---���һ���������Ƿ���ָ��������
	���򷵻�true��û���򷵻�false
	console.log("test" in obj);	//true
#### ��������
	Ŀǰ������Ҫ��������ṩ�Ķ���
	BOM DOM 
	���磺console.log() document.writer()
#### �ڽ�����
	ES��׼�ж���Ķ����κε�ES������ʵ��
	���磺Math String Number Boolean Function Object
### �����������ͺ�������������
	�����������͵�ֵ��ջ�ڴ��д洢������֮�以��Ӱ��
	�����������͵�ֵ�ڶ��ڴ��д洢��ÿ�����󴴽�һ���µĿռ䣬ջ�ڴ��б�����Ƕ���ĵ�ַ
	===
	�Ƚ����������������͵���ֵʱ���Ƚϵ�����ֵ
	�Ƚ�����������������ʱ���Ƚϵ������ַ����ַ��ͬ����false
### ����������
	var obj={};	//ʹ����������������
	�﷨��var obj2={name:"zhangsan",
			age:20,
			sex:"male"};
### ����
	1��var fun=new Function();	//���캯��
	2��function fun(){
		};
	3��var fun=function(){		//��������
		};
#### ��������
	function sun(a,b){
	consloe.log(a+b)
		}		//������������ʵ������
	sum(123,"hello");	//123hello
#### ����ֵ
	return �������κ�ֵ��
#### ʵ�ο������κ�ֵ
### ������
####	1��ȫ��������
	- ��ҳ���ʱ������ҳ��ر�ʱ����
	- ȫ����������һ������������Ķ���window������ֱ��ʹ�ã������������Զ��ᱣ����window��
	- var a = 10;
	- function fun(){
		alert("");
		}
	- console.log(window.a);	//10
	- consloe.log(window.fun());
	==========
	����������ǰ��
	��js�У���var�����ı������������д���ִ��֮ǰ���������ǲ��ḳֵ��
	����������ǰ��
	- ʹ�ú������������ĺ���function ������(){}�������д���ִ��ǰ��������������ǰ���á�
	- ʹ�ú������ʽ�����ĺ���var ������=function(){}�����ᱻ������ǰ
####	2������������
	- ÿ����һ�κ������ᴴ��һ���µĺ����������໥����
	- �ں����������п��Է��ʵ�ȫ��������ȫ�������򲻿��Է��ʺ���������
	- �ں����������в���һ������ʱ�����ڱ�������Ѱ�Ҹı������еĻ�ֱ��ʹ�ã�û��������һ����������Ѱ�ҡ�
	==========
	- �ں����������У�û����var�����ı�������ȫ�ֱ���
	- ����һ���β��൱���ں���������������һ������
### �ݹ�
	
#### debug
	�ϵ���Դ���
### this����
	- �������÷�ʽ��ͬ��thisָ��ͬ�Ķ���
	- �Ժ����ķ�ʽ���ã�thisָ��window
	- �Է����ķ�ʽ���ã�thisָ��ķ������ڵĶ���
### ����������������
	function creatPerson(name,age,sex){
		var obj=new Object();
		obj.name=name;
		obj.age=age;
		obj.sex=sex;
		obj.sayName=function(){
			console.log(this.name)
		};
		return obj;
	}
	var obj1=creatPerson("Bob",18,"male");
	obj1.sayName();
	- ����ģʽ�����Ķ���ʹ�õĹ��캯������object�����������ֶ��ֶ����޷��������ʶ�������
### ���캯�� 10.25
	function Person(name,age,gender){
		this.name=name;
		this.age=age;
		this.gender=gender;
		this.sayName=function(){
			alert(this.name);
		};
	}
	function Dog(name,age){
		this.name=name;
		this.age=age;
		this.sayName=function(){
			alert(this.age);
		}
	}
	var per=new Person("Bob",21,"male");
	var dog=new Dog("John",20);
	//console.log(per.sayName());
	//console.log(dog.sayName());
	==================
	- ������ʽ�Ĵ�������
	- ֱ�ӽ����Ը�ֵ��this(�´����Ķ���)
	- û�з���ֵ
	- instanceof���Լ��һ�������Ƿ���һ�����ʵ��
### Object.keys()����
	function Person() {}
	Person.prototype.name = 'aa';
	Person.prototype.age = 10;
	Person.prototype.gender = 'male';
	Person.prototype.sayName = function() {
		console.log('aaa');
	}
	var keys = Object.keys(Person.prototype);
	console.log(typeof keys); // ���һ���������
### toString()
	���������ʱ�������ϣ����[object][object],�������һ��toString()����
	function Person(name,age,gender){
		this.name=name;
		this.age=age;
		this.gender=gender;
	}
	
	
	Person.prototype.toString=function(){
		return this.name;
	}
	var per=new Person("Bob",21,"male");
	var per2=new Person("Amy",21,"fmale");
	console.log(per); 
	console.log(per2);
### ��������10.26
	var obj=new Object();
	obj=null;	//������ʹ�õĶ�������Ϊnull��js���Զ�����
### DOM
	ͨ��id����Ԫ�أ�
		var x=document.getElementById("intro");
	ͨ����ǩ������ HTML Ԫ�أ�
		var x=document.getElementById("main");
		var y=x.getElementsByTagName("p");
### BOM
	
### ������� 10.30
 	var arr=new Array();
	arr[0]=10;
	arr[1]=11;
	console.log(arr.length);	//2��length��ֵ��������һ	
	arr.length=1;
	console.log(arr);	//10 
	arr.length=3;
	console.log(arr);	//10,11,, length��������ʱ��Ѷ���Ŀճ���
	arr[arr.length]=12;
	arr[arr.length]=13;	//����������Ԫ��
#### ����������
	var arr=[1,2,3,4,5];	//һ��ʹ����������������
	var arr=new Array(1,2,3);
	����Ԫ�ؿ�����������������
	arr=["hello",123,null,undefined]
	//����
	var obj={name:"Bob"};
	arr[arr.length]=obj;
	console.log(arr);	//1,2,3,[object Object]
	//����
	arr=[function(){},function(){}];
	console.log(arr);	//function (){},function (){}
	//����
	arr=[[1,2,3],[4,,5,6]];
#### ����ķ���
	- push����:
	������������Ԫ��
	var arr=["Bob","Amy","John"];
	arr.push("Jack"); 	//push���Ԫ��
	console.log(arr);	//
	var result=arr.push("Jack"); 
	console.log(result);	//4  result���ظ��º�����ĳ���
	- pop����:
	ɾ����������һ��Ԫ��
	var arr=["Bob","Amy","John"];
	arr.pop();
	console.log(arr);	// Bob��Amy
	var result=arr.pop();
	console.log(result);	//John result����ɾ����Ԫ��
	- unshift����:
	�������һλ���Ԫ��
	var arr=["Bob","Amy","John"];
	arr.unshift("Jack");
	console.log(arr);	
	result����ֵ��push��ͬ
	- shift����
	ɾ������ĵ�һ��Ԫ��
	var arr=["Bob","Amy","John"];
	arr.shift();
	console.log(arr);	//
	result����ֵ�Ǳ�ɾ����Ԫ��
#### �������
	function Person(name,age){
		this.name=name;
		this.age=age;
	}
	
	
	Person.prototype.toString=function(){
		return this.name+" "+this.age;
	}
	var per=new Person("zh",15);
	var per1=new Person("zc",18);
	var per2= new Person("hz",22);
	var arr=[per,per1,per2];
	function gentel(arr){
		var newArr=[];
		for(var i=0;i<arr.length;i++){
			
		if(arr[i].age>=18){
			newArr.push(arr[i]);
		}
		} 
		return newArr;
	}
	var result=gentel(arr);
	console.log(result);
#### forEach()
	var arr=["zh","zc","hz"];
	arr.forEach(function(value,index,obj){
		console.log("value="+value);
	});
	- function����������ã���Ϊ�ص�����
	- ��������ʵ��,
	����ֵ����������������
#### �����ж�
	var arr0 = {
		name: 'zhanghuan',
		age: '20'
	}
		
		var arr = [1,2,3];
		console.log(arr0);
		//console.log(arr0.__proto__.constructor);
		//�ж��Ƿ���һ������
		1��//console.log(Array.isArray(arr0));
		2��//console.log(arr0 instanceof Array);
		3��//console.log(Array.prototype.isPrototypeOf(arr));
		4��//console.log(arr.constructor);
	 5��function isArrayFour(arr) {
           		if(typeof(arr) === "object") {
               	 		if(arr.concat) {
                   	 	return 'This is Array' 
              		  	}else {
                    		return 'This not Array' 
                		}
            		}
        	}
       		console.log(typeof(obj))
#### JSON
	JSON�ַ�����JS�ַ��������������ڣ�JSON�ַ���������˫����
##### ����
	������������
		var person = {
			name: "zhanghuan",
			age: 22	
		}
	��׼JSON��ʽ��
		var object = {
			"name": "zhanghuan",
			"age": "20"	
		}
	JSON���������ֵ�����˫����
##### ����
	var p = [
		{"name": "zhanghuan"},
		{"age": "20"},
		{"gender": "male"},
		{"address": "˷��"}
	]
##### JSON���л�
	JSON.stringify( ); //JS�������л�ΪJSON�ַ���
	JSON.parse(jsonText); // JSON�ַ���ת��ΪJS����
	
	���˽��
	var person = {
		"name": "zhanghuan",
		"age": 20,
		"gender": "male",
		"address": "˷��"
		}
	var b = JSON.stringify(person,["name","age"]);
	console.log(b);
### ������
#### 3.toString()   3..toString()   3...toString() ����������ʲô
	�ֱ�Ϊ3��error��erroe
#### ����ȥ��
	var arr = [1,2,3,44,55,1,3,44];
	var i,t;
	var newArr = [];
	for(i=0;i<arr.length;i++){
		if(newArr.indexOf(arr[i])=-1){
			newArr.push(arr[i]);
		}
	}
	console.log(newArr);

	