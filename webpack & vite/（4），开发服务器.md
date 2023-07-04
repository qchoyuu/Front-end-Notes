>监听打包
* 当我们在工作中，可能会频繁进行打包，这时候通过命令
  * `npm webpack --watch` 坚挺源代码更改自动打包
* 也可以设置为package配置文件
  * ```javascript
      "scripts":{
         "build":"webpack",
         "watch":"webpack --watch"
      }
      ```
* 通过 `yarn webpack serve` 则可以将项目运行在服务器上，并且修改代码，通过监听实现自动更新
* 通过 `yarn webpack serve --open` 则可以直接将项目打开在浏览器
* 注意：使用`yarn webpack serve`打包发现项目中并没有disz文件，因为是将代码打包在服务器，在服务器中运行的，所以在最终开发结束部署，需要手动build一下