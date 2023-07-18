```javascript

//匹配 acd 和 abcd路径（就是b可加可不加）
app.get('/ab?cd',function(req,res){
   res.send("ab?cd")
})


//匹配动态参数，比如拿到列表某一项，传递id获取详情
app.get('/ab:id',function(req,res){
   res.send("ab?cd")
})

//表示b可以匹配多次，如 abcd，abbcd，abbbbbbcd
app.get('/ab+cd',function(req,res){
   res.send("ab?cd")
})


//表示在bc中可以随便写比如 abxcd，ab123cd
app.get('/ab*cd',function(req,res){
   res.send("ab?cd")
})

//表示bc必须一起，一起不写或者一起写
app.get('/a(bc)?d',function(req,res){
   res.send("ab?cd")
})

//也可以使用正则表达式来限制路由
app.get(/ .*fly$/,function(req,res){
   res.send("ab?cd")
})



```