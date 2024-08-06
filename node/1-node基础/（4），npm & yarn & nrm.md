
>npm
- npm的基本使用
  ```
  1. 自定义模块 -> 我们自己书写的js文件

  2. 内置模块 -> 就是安装node的时候自带的一些模块,node原生的模块

  3. 第三方模块 -> 其他人写好的一些js文件，里面放好一些功能,需要的时候下载下来，再使用
  ```
- npm常用命令
  ```
  1. npm install 包名 → 简写： npm i 包名

  2. npm uninstall 包名 → 间歇 ： npm un 包名

  3. npm cache clear -f ：清除缓存

  4. npm cache 文件夹 ：删除本地
  ```

>yarn
```
1. 安装： npm install -g yarn

2. 对比npm： 速度超快，超级安全，会通过算法校验安装包的完整性

3. 添加依赖包：yarn add md5

4. 升级依赖包：yarn upgrade 

5. 移除依赖包：yarn remove

6. 安装项目全部依赖：yarn install
```

>nrm
```
1. npm 的下载地址默认在国外，下载会比较慢容易丢包，解决方法就是换一个国内的下载地址
  （1）. npm地址，国外地址
  （2）. yarn 地址，国外地址
  （3）. cnpm地址，中国国家做的镜像
  （4）. taobao地址，阿里做的镜像
  
2. 安装：npm install nrm —global - mac：sudo npm install nrm —glgbal

3. 检测是否安装成功：nrm —version

4. 卸载：npm uninstall nrm —glgbal

5. 使用：nrm test

6. 下载nrm报错解决方式：npm install -g nrm open@8.4.2 --save

7. 切换npm 下载地址：nrm use 下载地址名称

8. 切换完成以后，再次使用npm下载内容的时候，就是切换后的下载地址
```

>cnpm
```
直接指向淘宝镜像，需要安装
```

> nvm

```
-> 前往github下载安装nvm

1.nvm -v：查看安装版本

2.nvm list ：查看安装的各个node版本

3.nvm install 18.20.2：安装node指定版本

4.nvm use 18.20.2：切换到指定版本

```