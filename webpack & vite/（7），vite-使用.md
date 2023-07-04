>vite的使用
* 初始化package.json文件 `yarn init -y（-y 表示 yes）`
* 安装vite `yarn add -D vite`
* 创建一个`index.html`可以不需要src目录
* 再次创建js文件`index.js`
* `index.html`引入js文件，`<script type:"module"></script>`使用vite必须添加type属性
* 通过命令启动`yarn vite`启动一个开发环境的服务器，会发现速度非常的块，那么就是因为vite并没有进行打包的操作，仅仅是直接在本地启了服务器
* vite打包命令`yarn vite build`
* 运行打包后的代码 `yarn vite preview`
* 可以通过package.json中的script配置命令
* 使用vite创建 vue/react..等项目
  * npm：`npm create vite@latest`
  * yarn: `yarn create vite` 