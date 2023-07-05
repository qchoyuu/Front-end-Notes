
>ListPage
```javascript

import Link from "next/link"

export default function ListPage () {

   const data = [
      {
         id:1,
         name:'第一个数据'
      },
      {
         id:2,
         name:'第二个数据'
      },
      {
         id:3,
         name:'第三个数据'
      },
   ]

   return (
      <div>
         <div>这是List</div>
         <ul>
            {data.map((item) => (
               {/* 1.点击跳转到list/[id]路由 并且传递了name参数 */}
               <li key={item.id}><Link href={'/list/' + item.id + '?name=' + item.name}>{item.name}</Link></li>
            ))}
         </ul>
      </div>
   ) 
} 
```

>[id]Page
```javascript
'use client'

import { useParams,useSearchParams } from 'next/navigation'
export default function MhyData () {
   const { id } = useParams()
   {/* 2.通过useSearchParams方法则可以获取到传递的name参数 */}
   const searchParams = useSearchParams()
   return (
      <div>
         list ----- {id}
         <p>{searchParams.get('name')}</p>
      </div>
   )
}
```