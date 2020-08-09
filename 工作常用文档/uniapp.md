### webapp
  webapp加壳变成原生应用, 如果想要变成Android应用,需要加Android壳,这个壳需要专门android开发人员进行开发
  webapp如果想要变成ios应用,需要加ios的壳,这个壳需要ios开发人员开发
### 用uniapp开发小程序时配置hbuilderX工具
    在uniapp官网下载hbuilderX开发版, 参考word文档配置小程序的安装目录
### 基础文件分析
  * manifest.json文件 是全局配置, 包括小程序配置等
  * pages.json 页面路径配置,和局部配置
  * uni.scss封装的一些scss全局变量,可用可不用, 用到几率不高
  * main.js 整个项目的入口文件
  * App.vue代表的是整个应用  等同于app.js加上app.wxss
  * static静态资源
  * pages是页面  一个vue页面代替了原生小程序的wxml, js, wxss
    结构用的都是uniapp的组件, 按F1可以查看文档
    结构既支持uniapp的组件又支持原生html标签,建议最好用组件
  * unpackage 把编译完的文件放在这个文件夹中
### uniapp中使用stylus
    <style lang="stylus">
    在uniapp中使用stylus是不需要单独装包的, hbuilder内置有一些插件
    工具===> 插件安装===> 安装stylus插件
    插件市场的插件使用===> 使用hbuilderX导入插件
### uniapp中的适配单位
  upx 等同于原生小程序的rpx
### uniapp中项目在浏览器端跨域的问题(在vue中解决跨域)和小程序中的区别
    解决浏览器中跨域要配置代理,不能用完整路径,加上api
    和小程序不同 小程序是: config.host+url 没有/api
### uniapp中使用图标
    icon 不好调节, 我们可以用我们自己的字体图标库
    





