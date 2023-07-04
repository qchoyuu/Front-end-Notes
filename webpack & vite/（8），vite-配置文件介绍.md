>vite的向下兼容
* 与webpack一样的问题，源码中使用箭头函数，打包后也是箭头函数
* webpack是安装了babel插件
* vite如果配置？
  * 创建`vite.config.js`文件
  * 安装legacy插件：`yarn add -D @vitejs/plugin-legacy`
  * 还需要安装一个压缩代码的插件：`yarn add -D terser`
  * ```javascript
      import { defineConfig } from 'vite'
      import legacy from '@vitejs/plugin-legacy'
      
      export default defineConfig({
        plugins:[legacy({
          targets:["defaults","ie 11"]
        })]
      })
    ```