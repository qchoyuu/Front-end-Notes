>直接再命令行书写js代码
```
1. 打开命令行,输入指令 node 回车
2. 进入输入状态,只能书写js代码，其他代码会报错,等价于在浏览器的控制台
3. 缺点：
  -> 没有代码提示
  -> 不能存下来
4. 退出编辑状态，ctrl + c 按下两次
```
<br/>

>运行js文件
```
1. 把js代码书写在js文件中
2. 打开命令行，切换目录到你要执行的js文件所在的目录
3. 书写执行node 文件名称 回车
```

<br/>

>javaScript与node.js
```
浏览器中的JavaScript
ECMAScript + Web Api （BOM，DOM）

而node.js
ECMScript + Node API（fs，http，path..等等），所以是不能编译BOM和DOM的，但是可以使用console和定时器API
Node中的顶级对象为global，也可以用globalThis访问顶级对象
```