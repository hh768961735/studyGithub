#### ES6������
###  const��let
	function getClothing(isCold) {
 		 if (isCold) {
    			var freezing = 'Grab a jacket!';
  		} else {
   		 	var hot = 'It's a shorts kind of day.';
   			console.log(freezing);
  		}
	}
	getClothing(false);  
	���undefine,var�����ı�����������ǰ
	freezing������������û�и�ֵ���������undefined,����var��ȱ�㡣
	// ��const��let�����ı�������������ǰ,ֱ�ӱ���
	// let���Բ���ʼ��,����֮��ֱ�Ӹ�ֵ����,�����ٴ�����(ͬһ��������)
	// const�����ʼ��,ͬһ�������ڲ������������Ҹ�ֵ
	function getClothing(isCold) {
 		 if (isCold) {
    			const freezing = 'Grab a jacket!';
  		} else {
   		 	const hot = 'It's a shorts kind of day.';
   			console.log(freezing);
  		}
	}
	����getClothing(false),����̨������Ϊfreezing����else�������У�
	û�б�������const��let���ᱻ������ǰ��
	+ let���������������¸�ֵ�����ǲ�����ͬһ����������������(����������ֱ�Ӹ�ֵ)
	+ const�����ı��������ʼ����������ͬһ�����������������¸�ֵ
### class
#### ������
	class Rectangle {
		constructor(height,width){
			this.height = height;
			this.width = width;
		}
	}
#### ��������
	������������ǰ����Ҫ�������࣬�ڽ���ʵ����������
	let p = new Rectangle(); 
	// ReferenceError
	
	class Rectangle {}
### ����ʽ
	<!-- ������ -->
	let Rectangle = class{};
	<!-- ������ -->
	let Rectangel = class Rectangle{}
### ���巽���Ͷ���
#### �ϸ�ģʽ(use strict)
	������������ʽ�����嶼ִ�����ϸ�ģʽ�¡����磬���캯������̬������ԭ�ͷ�����getter��setter�����ϸ�ģʽ��ִ�С�
#### ���캯��
	constructor���������ڴ����ͳ�ʼ��һ����class�����Ķ���һ����ֻ����һ��constructor������
	һ�����캯������ʹ�� super �ؼ���������һ������Ĺ��캯����
#### ԭ�ͷ���
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
#### ��̬����
	<!-- ��̬��������ֱ��ͨ���������ã�����Ҫʵ�����࣬ͨ������Ϊһ��Ӧ�ó��򴴽����ߺ��� -->
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

	