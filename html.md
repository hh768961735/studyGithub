### 1、五大浏览器内核
1、Trident内核：代表作品是IE，因IE捆绑在Windows中，所以占有极高的份额，又称为IE内核或MSHTML，此内核只能用于Windows平台，且不是开源的。
代表作品还有腾讯、Maxthon（遨游）、360浏览器等。但由于市场份额比较大，曾经出现脱离了W3C标准的时候，同时IE版本比较多，
存在很多的兼容性问题。

2、Gecko内核：代表作品是Firefox，即火狐浏览器。因火狐是最多的用户，故常被称为firefox内核它是开源的，最大优势是跨平台，在Microsoft Windows、Linux、MacOs X等主 ??要操作系统中使用。
?Mozilla是网景公司在第一次浏览器大战败给微软之后创建的。有兴趣的同学可以了解一下浏览器大战

3、Webkit内核：代表作品是Safari、曾经的Chrome，是开源的项目。

4、Presto内核：代表作品是Opera，Presto是由Opera Software开发的浏览器排版引擎，它是世界公认最快的渲染速度的引擎。在13年之后，Opera宣布加入谷歌阵营，弃用了 ? ?Presto

5、Blink内核：由Google和Opera Software开发的浏览器排版引擎，2013年4月发布。现在Chrome内核是Blink。谷歌还开发了自己的JS引擎，V8，使JS运行速度极大地提高了
### 2、cookies和webStorage
	相同点：都存储在客户端
	不同点：
	1、cookie大小不超过4k
		sessionStorage和localStorage能达到5M
	2、有效时间
		localStorage存储持久数据，关闭浏览器后数据依然存在
		sessionStorage在关闭浏览器后数据自动删除
		cookie的数据在过期之前一直有效
	3、交互方式
	cookie的数据会传递到服务器，服务器也可以写到客户端
	webStorage的数据尽在本地保存