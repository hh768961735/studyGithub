###  3.toString()   3..toString()   3...toString() 的输出结果是什么
	分别为3，error，erroe
### 数组去重
	var arr = [1,2,3,44,55,1,3,44];
	var i,t;
	var newArr = [];
	for(i=0;i<arr.length;i++){
		if(newArr.indexOf(arr[i])=-1){
			newArr.push(arr[i]);
		}
	}
	console.log(newArr);