>ES模块化写法
```
1. 
  问题：当我们想要在A.js中使用B.js的方法，可以在A.js中引入B.js
  
    （1）按照commonJS的开发方式：
        let B = require('./B')
        
    （2）但是通过模块化的方式使用：
        import B from './B.js' （会报错，提示需要在package文件中添加"type" = "module"）
        
        （2.1）生成package.json文件： npm init
        （2.2）添加： "type" = "module"
        （2.3）导出B： export default B; 
        （2.4）引入B： import B from './B.js';
        （2.5）导出多个方法：export {A,B,C}
        （2.6）导入多个方法：import { A,B,C} from './B'
      
        
2. commonJS 与 ES模块化不可以联用
```