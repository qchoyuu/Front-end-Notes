>nextJS使用基于文件系统的路由器，其中使用文件夹来定义路由
```
1.app文件夹中每个文件夹代表一个映射到URL的路由段
2.要创建嵌套路由，就可以将文件夹相互嵌套
3.需要有一个特殊的文件 page.js 就可以公开访问路由段

访问dashboard 则展示相应的page.js
访问analytics 则404因为没有可访问的page.js

```

>pages & layouts

* pages
  * 文件夹就是路由段
  * `page.js`则就是该路由段展示的ui内容
  * page文件后缀可以是`js / tsx / jsx`
  * 默认情况下，页面是`服务器组件`，但可以设置为`客户端组件`


* layouts
  * layout文件是在多页面之间共享的组件
  * 导出layout文件中的react组件
  * 该组件接收一个children，可在渲染期间填充子布局，或子页面
  ```javascript
   export default function DashboardLayout ({children}:{children:React.ReactNode}){
      return (
         <section>
            {children}
            DashboardLayout
            <Setting></Setting>
         </section>
         )
      }
  ```