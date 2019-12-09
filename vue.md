### Vue实例
	new Vue({
	  el: '#app',
	  data: obj
	})
### 生命周期
	new Vue({
	  data: {
	    a: 1
	  },
	  created: function () {
	    // `this` 指向 vm 实例
	    console.log('a is: ' + this.a)
	  }
	})
	// 也有一些其它的钩子，在实例生命周期的不同阶段被调用，
	如 mounted、updated 和 destroyed。生命周期钩子的 this 
	上下文指向调用它的 Vue 实例。
### 模板语法
#### 插值
		<span>Message: {{ msg }}</span>
		v-once指令，插值不会改变。
		<span v-once>这个将不会改变: {{ msg }}</span>
#### 原始 HTML
		双大括号会将数据解释为普通文本，而非 HTML 代码。为了输出真正的 HTML，你需要使用 v-html 指令：
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
