>安装 express
`npm install -g express-generator`

>配置使用 ejs
`express myapp --view=ejs`

>第三方中间件 
```javascript
   安装：npm i cookie-parser

   var coolieParser = require("cookie-parser");

   app.use(cookieParser()); //注册第三方cookieParser中间件

   //读取前端cookie值
   req.cookies

   //设置前端的cookie值
   res.cookie("gender","male")
```