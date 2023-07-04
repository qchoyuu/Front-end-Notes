>服务器端代码调试
* 如上节，我们通过`yarn webpack server`进行了服务器端打包
* 这时我们在浏览器中调试代码，会发现着时候的代码则是打包后的代码，是不可调试的，因为调试只能调试源码
* ```javascript
    const HTMLPlugin = require("html-webpack-plugin")

   modele.exports = {
      //1.需要切换为开发模式developent
      mode:"development",
      output:{},
      module:{},
      plugins:[
         new HTMLPlugin()
      ],
      //2.配置需要使用的开发工具，该工具为source-map
      devtool:"inline-source-map"
   }

   ```
* 如上配置则可以在服务器打包后进行源码调试