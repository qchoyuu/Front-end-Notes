## nextJS 13.4路由新写法

>一，创建路由
1. 在 `src/app` 目录下创建 `about` 文件夹
2. 在 `about` 文件夹下创建固定文件 `page.tsx`
3. 访问路径 `about` 则就会展示对应的 `page.tsx` 的内容


>二，layout文件
 1. 当我们继续在 `about` 文件夹中创建 `layout.tsx` 文件
 2. 会发现 `about` 文件夹中的 `page.tsx` 文件不生效了
 3. 只展示了 `layout.tsx` 的内容
 4. ```javascript
      import React from 'react'

      function ListLayout({ children }:{children:React.ReactNode}) {
         return (
            <div>
               <h1>这是layout</h1>
               {children}
            </div>
         )
      }

      ```
  5. 会发现 `layout.tsx` 是将对应的 `page.tsx` 嵌套进来了



>三，动态路由
1. 创建一个 `[id]` 的文件夹，当然也创建对应的 `page.tsx`
2. 此时随便在路径中输入内容，则就会跳转到 `[id]` 这个路由中
3. 我们可以通过 `import {useParams} from next/navigation`
4. 结构出来传递的参数 `const {id} = useParams();`


>四，切换客户端方法
1. nextJS默认为服务器端输出，所以客户端的方法是用不了的
2. 比如 `useEffect,const {id} = useParams().. `
3. 所以需要在组件最开始添加 `use client`

>五，_components文件
1. 我们在app中写的文件夹都会被解析为路由
2. 但是我们存放公共组件或者静态资源的文件夹可以通过前缀添加下划线_
3. 如此`_component,_utils..`nextJS则不会解析为路由

>六，服务端组件和客户端组件
1. 在 `_component` 组件文件夹中创建了一个 `Data.tsx`组件，他是一个客户端组件（use client）
2. 但是引入在了一个服务端组件，则服务端组件打印的数据是在终端，而客户端是在控制台