>使用客户端组件请求数据
```javascript

   'use client'
   import { useEffect } from 'react';

   function ListPage() {

      useEffect(() => {
         fetch(
            'https:..' //请求接口
         )
         .then((res) => res.json())
         .then((res) => {
            console.log(res)
         })
      })
   }

   /**
    * 问题：
    *    这个接口是米哈游的接口，所以对我们客户端会进行跨域的限制
    *    我们可以通过使用服务端组件进行获取
    */

```

>使用服务端组件请求数据
```javascript 

   const loadDataFromMHY = () => {
      return fetch(
         'https:....'
      )
      .then((res) => res.json())
   }

   async function ListPage() {
      const mhyData = await loadDataFromMHY();
      console.log(mhyData)
      
   }
   
   /**
    * 会将数据打印在终端
    * 
    */

```