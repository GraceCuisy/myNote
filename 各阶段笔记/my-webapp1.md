# my-webapp-project
### vue的devServer选项支持所有的webpack的devServer
### 静态mock与动态mock
  1. 静态mock,里面的数据不会发生改变
    webpack的devServer.before

  2. 动态mock,使用mock.js实现,里面的数据可以发生改变
### 在整个vue的脚手架里面,有三种文件后缀可以省略
    .vue .js .json
### 一级路由要在一级组件中渲染

### stylus使用
    靠缩进写样式
  在stylus中写大括号,分号,冒号,也是可以的,但是不推荐
  stylus中如何引入另外的stylus文件 通过@import 路径中不能使用别名
### stylus使用与less区别
  定义混合 less的混合都是以.为开头的
          stylus的混合不是以.为开头的
  stylus 中的变量是$修饰  less中是@
  stylus中变量拼接,变量直接加字符串就行,像写js一样
### 自定义字体
    自定义字体是可以保证所有的用户都使用上我们网站的字体,
    因为字体是需要去我们的服务器上下载的
  
    课上操作: 花了一个矢量图,把这个矢量图和字母T做了一个绑定,导出字体
    导出的字体只能管一个T字符
### 字体图标
    字体图标也是字符,只不过这个字符绑定了一张矢量图, 
    比如我们的项目需要100个图标,我们可以给100个字符一一对应绑定100张矢量图, 然后生成一个字体文件,我们项目中放一个字体文件就可以了. 如果不这样做,需要用户向服务器请求100次图片
  **现在操作**  有很多成熟的做图标的网站 IcoMoon
                icomoon.io
  注意: 大部分公司不会直接依赖阿里
      我们把他们的图标下载下来使用,不使用他们的服务器
### npm i 的使用
### 组件本质就是一个自定义的html标签
### 非props特性的属性和props特性的属性
    一个组件标签(一个组件)肯定是要被它的模板所覆盖掉的,当模板去覆盖组件的时候,要去看一下组件标签上的属性
    非props特性的属性会被模板继承下来
### css经典布局 粘连布局
   又被称为stick footer布局
   如果页面内容不够长的时候,页脚块粘贴在视窗底部,如果内容足够长时,页脚块会被内容向下推送
   
   不能让footer脱离文档流
### 预处理器的继承与混合的区别
    预处理器的继承只能继承class
    使用场景
      1.当公共样式都是一些静态样式不需要传参的 使用继承
        清除浮动使用继承
      2.当公共样式中有一部分需要变化的样式  使用混合
  **stylus中继承和less中继承**
      stylus中: @extend .clearfix
        默认就会继承这个class中的所有内容
      less中: #wrap:extend(.clearfix all){}
          或者 &:extend(.clearfix all)
      less中要加all
### 当前元素模糊和元素后边的背景内容模糊
    filter blur(7px)
    backdrop-filter blur(7px)
### 使用插槽的好处
  父组件使用子组件时,子组件中定义一个插槽, 父组件传一个对应html片段覆盖子组件中的插槽
  因为外部使用时是传入的html片段,所有这个html的样式外部可以自己自由指定,子组件中也可以有默认样式 外部不指定样式时,以内部默认样式为主,传了之后以外部样式为主
