>get：(params)
```javascript
const express = require("express");
const router = express.Router();

//响应后，返回login-success
router.get("/",(req,res) => {
   console.log(req.query)
   res.send("login-success")
})

module.exports = router

```


>post:(body)
```javascript
/**
 * index.js
 * 1. 配置post解析参数的中间件
 * 
 */

const express = require("express");
const app = express();
const LoginRouter = require("./route/LoginRouter")

//配置解析post参数的，不需要下载第三方，内置：
app.use(express.urlencoded({extended:false}))  //post参数为www-form-urlencoded类型
app.use(express.json()) //post参数为json类型

app.use(function(req,res,next){
   console.log("验证token")
   if(true){
      next()
   }else{
      console.log("验证失败")
   }
})

app.use("/login",LoginRouter)

app.listen(3000,()=>{
   console.log("server start")
})



--------------------------------

/**
 * LoginRoute.js
 * 
 */
const express = require("express");
const router = express.Router();

router.get("/",(req,res) => {
   res.send("login-success")
})

//通过req.body获取参数
router.post("/",(req,res) => {
   console.log(req.body)
   res.send({ok:1})
})

module.exports = router

```