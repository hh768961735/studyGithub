###  const与let
	function getClothing(isCold) {
 		 if (isCold) {
    			var freezing = 'Grab a jacket!';
  		} else {
   		 	var hot = 'It's a shorts kind of day.';
   			console.log(freezing);
  		}
	}

	运行getClothing(false),控制台输出undefined，因为变量声明提前，
	freezing被声明，但是没有赋值，所以输出undefined,这是var的缺点。

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