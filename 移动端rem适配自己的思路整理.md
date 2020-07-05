750/16rem    675/16rem

rem就是一个中介 html根标签的字体大小是1rem

页面中加上<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0>
实现了在iphone6上布局视口是375px, 在ipone4上布局视口是320px

把375布局视口看成是16rem  计算出1rem对应的px设为html的字体大小

把750设计图看成是16rem 计算出某个元素应该占据的比例(占据多少rem) 
写样式时,css单位用rem  网页中会用rem*html根标签的字体大小, 就把一个元素转化为了布局的css单位 

rem就是一个天平 它能计算1位图像素在不同屏幕上应该占据多少css像素

在vue项目中使用 lib-flexible 和 postcss-px2rem

lib-flexible 会使用淘宝的适配方案,将屏幕的布局视口大小分成10份, 给html标签加上字体大小

而postcss-px2rem 可以将我们写的位图像素转化为rem 
但是postcss-px2rem需要我们指定(1rem代表多少的位图像素)remUnit: 75   //remUnit = 设计稿/等分数10， 网易严选首页750宽，正好相当于是设计稿宽度，所以值为750/10 = 75

********
做完这些之后, 我们需要在项目中需要在index.html中加上<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0>
从而覆盖掉lib-flexible自带的meta标签,(解释:用我们自己的meta标签我们自己好控制, 用插件的meta标签我们没法控制)
然后设计图上是多少位图像素,我们在样式中就写多少px就行了  有postcss-px2rem和 lib-flexible 帮我们把我们写的位图像素转化为页面布局视口的css像素

如果在vue项目中使用vant,mintUI等移动端UI库,他们本身就做了移动端适配,所以要配置postcss-plugin-px2rem或postcss-px2rem忽略对他们的转化 
postcss-plugin-px2rem配置 exclude: /(node_modules)/, 