### webpack相关
  **为什么要使用构建工具?**
  (1)ES6的模块化语法,浏览器不认识
  (2)js中的新语法,浏览器不认识
  (3)js css的兼容性问题
  (4)压缩,语法检查
  构建工具的意义: 
    我们不用构建工具,写的代码也能在浏览器端运行,只是效率比较低,并且兼容性不好,
    使用构建工具之后可以让程序员写的源代码,经过加工生成大多数浏览器都认识的,精简的,高效的代码

  使用webpack的时候需要下载webpack和webpack-cli  秘书干活

  1. ES6的import和export语法直接在浏览器端运行是会报错的,
    但是webpack本身就能去编译ES6和commonJS的模块化语法,但是不能编译普通的ES6语法
    编译普通ES6语法需要引入其他工具包
    需要让webpack理解babel,就需要有babel-loader
  2. 关于babal理解
    babel/core本身不编译ES6语法,babel是基于一系列插件来做ES6语法的编译
    每个语法都对应一个babel的插件来编译对应的语法
    一个babel preset是包含多个常用的babel plugin的插件的集合包
  3. 一个loader需要在module rules的数组中写一个对象
  4. webpack核心概念
      entry  output
      module:{  配置loader loader 让 webpack 能够去处理那些非 JavaScript 文件（webpack 自身只能解析 JavaScript）
        rules:[
          {} //每一个对象为一个loader配置
        ] 
      }
      plugins //插件则可以用于执行范围更广的任务。插件的范围包括，从打包优化和压缩，一直到重新定义环境中的变量等。
      Mode：模式，有生产模式production和开发模式development
  5. 处理less文件需要loader: less-loader css-loader style-loader
     处理css资源 css-loader style-loader
     处理图片文件 需要用到url-loader,url-loader是对file-loader的上层封装
     处理html中的<img>资源 需要html-loader
     处理其他资源(字体、音视频)等,需要用到file-loader

### 预处理器 less sass stylus的使用和区别
    