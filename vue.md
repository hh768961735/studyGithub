### Vueʵ��
	new Vue({
	  el: '#app',
	  data: obj
	})
### ��������
	new Vue({
	  data: {
	    a: 1
	  },
	  created: function () {
	    // `this` ָ�� vm ʵ��
	    console.log('a is: ' + this.a)
	  }
	})
	// Ҳ��һЩ�����Ĺ��ӣ���ʵ���������ڵĲ�ͬ�׶α����ã�
	�� mounted��updated �� destroyed���������ڹ��ӵ� this 
	������ָ��������� Vue ʵ����
### ģ���﷨
#### ��ֵ
		<span>Message: {{ msg }}</span>
		v-onceָ���ֵ����ı䡣
		<span v-once>���������ı�: {{ msg }}</span>
#### ԭʼ HTML
		˫�����ŻὫ���ݽ���Ϊ��ͨ�ı������� HTML ���롣Ϊ����������� HTML������Ҫʹ�� v-html ָ�
		<div id="app">
			<p>{{ rawHtml }}</p>
			<p v-html="rawHtml"></p>
		</div>
		
		var app = new Vue({
			el: '#app',
			data: {
				rawHtml: "<span style = 'color: red'>This should be red.</span>"
			}
		})
