> 直接在命令行书写js代码

* 打开命令行，输入node回车即可进入输入状态
* 进入输入状态只能写入JS代码，其他代码会报错
* 缺点：
	* 没有代码提示
	* 不能保存在命令行写的代码
* 退出编辑状态，`CTRL + C`连按两次即可


>运行js文件

* 将js代码书写在.js文件中
* 打开命令行，切换目录到执行的js文件所在目录
* 根据命令`node 文件名`执行代码


>javaScript与node.js
```
JavaScript：
	ECMAScript + Web Api （BOM，DOM）


node.js
	ECMScript + Node API（fs，http，path..等等），所以是不能编译BOM和DOM的
	Node中的顶级对象为global，也可以用globalThis访问顶级对象
```