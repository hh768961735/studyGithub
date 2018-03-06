### 3.5
#### 数值转换
	1.number
	var num1 = Number("xxx");
	Number()函数的转换规则如下。  
	如果是 Boolean 值，true 和 false 将分别被转换为 1和 0。  	如果是数字值，只是简单的传入和返回。  
	如果是 null 值，返回 0。  
	如果是 undefined，返回 NaN。 
	2.parseInt
	var num1 = parseInt("xxx");
	var num1 = parseInt("1234blue");    // 1234 
	var num2 = parseInt("");            // NaN 
	var num3 = parseInt("0xA");         // 10（十六进制数） 	var num4 = parseInt(22.5);          // 22 
	var num5 = parseInt("070");         // 56（八进制数） 	var num6 = parseInt("70");         // 70（十进制数） 		var num7 = parseInt("0xf");         // 15（十六进制数）
 	实际上，如果指定了 16作为第二个参数，字符串可以不带前面的	"0x"，如下所示：  
	var num1 = parseInt("AF", 16);  //175 
	var num2 = parseInt("AF");   //NaN  
	var num1 = parseInt("10", 2);     //2  （按二进制解析） 	var num2 = parseInt("10", 8);      //8  （按八进制解析）	var num3 = parseInt("10", 10);     //10 （按十进制解析） 	var num4 = parseInt("10", 16);     //16 （按十六进制解析
	 parseInt()函数类似，parseFloat()也是从第一个字符（位置 0）开始解析每个字符。而且 也是一直解析到字符串末尾，或者解析到遇见一个无效的浮点数字字符为止。也就是说，字符串中的第 一个小数点是有效的，而第二个小数点就是无效的了，因此它后面的字符串将被忽略。举例来说， "22.34.5"将会被转换为 22.34。 
	parseFloat()与 parseInt()的第二个区别在于它始终都会忽略前导 的零。parseFloat()可以识别前面讨论过的所有浮点数值格式，也包括十进制整数格式。但十六进制格 式的字符串则始终会被转换成 0。由于 parseFloat()只解析十进制值，因此它没有用第二个参数指定基 数的用法。后还要注意一点：如果字符串包含的是一个可解析为整数的数（没有小数点，或者小数点后 都是零），parseFloat()会返回整数。以下是使用 parseFloat()转换数值的几个典型示例。  
	var num1 = parseFloat("1234blue");        //1234 （整数） 	var num2 = parseFloat("0xA");              //0 
	var num3 = parseFloat("22.5");             //22.5 		var num4 = parseFloat("22.34.5");          //22.34 		var num5 = parseFloat("0908.5");          //908.5 		var num6 = parseFloat("3.125e7");        //31250000 
####String 类型
	1.字符串用单引号双引号都可以
	var lastName = "Mike"
	var firstName = 'Mike'
	2.转换为字符串
	var age = 10;
	var ageAsString = age.toString();

	var num = 10; 
	alert(num.toString());      // "10" 
	alert(num.toString(2));     // "1010" 
	alert(num.toString(8));     // "12"
	alert(num.toString(10));    // "10" 
	alert(num.toString(16));    // "a"	
####Object类型
	1.var o = new Object();