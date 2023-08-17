```
如上我们像前端返回内容使用的是：

res.write()
res.end()

现在经过express封装可以直接通过:

res.send()

对比:

1.使用res.write() && res.end() 如果传递的是html片段，那么writeHeard里面就需要时html解析，如果是json则就需要时json解析
2.使用res.send()则不需要，因为已经进行了封装

```