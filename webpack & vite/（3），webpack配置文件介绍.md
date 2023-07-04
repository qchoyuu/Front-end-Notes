>webpack配置文件介绍
*  webpack会自动找寻src默认文件，打包则是dist默认文件
*  但是我们现在不想使用它的默认文件
*  需要在项目中创建`webpack.config.js`文件，这个文件就是配置文件
*  注意：`webpack.config.js`文件并不是前端文件，他是给node.js进行读取配置的，所以我们需要使用node.js（src中是前端的代码，src以外则就是node.js）
*  ```javascript
   //webpack.config.js

   const path = require("path")
   module.export = {
      //1.mode:设置打包模式，production表示生产模式，development表示开发模式
      mode:"production"，

      //2.entry:设置入口文件（默认是./src/index.js）
      entry:"./hello/hello.js",//用来指定打包时的主文件，默认为./src/index.js（修改为hello.js）
      //entry:["./src/a.js","./src/b.js"],//将src下的a和b一起打包
      //entry:{ a:"./src/a.js", b:"./src/b.js" }//分别打包src/的a.js和b.js

      //3.output:设置输出文件路径（打包到哪个文件夹下的那个文件）
      output:{
         path:path.resolve(__dirname,"dist"),//指定打包的目录，必须要绝对路径,默认则是dist
         filename:"main.js",//打包后的文件名
         //filename:"[name].js" //如果是分别打包文件，可以将打包后的文件成变量
         clean:true, //自动清理之前打包的文件
      },//配置打包后的地址

      /**
       * webpack默认情况下,只会处理js文件，如果我们希望他
         可以处理其他类型的文件，则要为其引入loader

         - 以css为例
            - 使用css-loader可以处理js中的样式
            - 使用步骤
               1. 安装那个：yarn add css-loader -D
               2. 配置：如下


         - babel：
            - 在编写js代码时，经常需要使用一些js中的新特性，而新特性在旧的浏览器中兼容并不好，此时导致我们无法使用一些新特性
            - 但是我们希望能够使用新特性，通过一些工具将新特性转换为旧代码
            - babel就是这样一个工具，可以将新的js语法转换为旧的js，提高代码的兼容性
            - 我们如果希望webpack支持babel，就需要想webpack中引入babel的loader
            - 使用步骤：
               1.安装 npm install - D babel.loader @babel/core @babel/preset-env
               2.配置：如下
       */

      //4.module：配置的是loader，对于不通文件进行处理
      module:{
         rules:[
            {
               test:/\.css$/i,
               use:["style-loader","css-loader"]//css
            },
            {
               test:/\.(jpg|png|gif)$/i,
               type:"asset/resoource"//图片资源类型
            },
            {
               test:/\.m?js$/,
               exclude:/(node_modules | bower_components)/,
               use:{
                  loader:"babel-loader",
                  options:{
                     presets:['@babel/preset-env']
                  }
               }
            }
         ]
      }
   }

   ```

   >plugin（插件）
   * 用来为webpack来扩展功能
   * `npm install -D html-webpack-plugin`
     * 这个插件可以在打包代码后，自动在打包目录生成html页面
     * 使用步骤：
       * 安装依赖
       * 配置插件
   * ```javascript
      const HTMLPlugin = require("html-webpack-plugin")

      modele.exports = {
         mode:"production",
         output:{},
         module:{},
         plugins:[
            new HTMLPlugin()
         ]
      }

      ```