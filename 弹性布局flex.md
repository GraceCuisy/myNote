### 前端坐标系比较复杂
    是因为前端坐标系方向会随着css属性改变
### flex两组核心概念
            容器 项目
            主轴 侧轴

### flex一条核心规则:
      项目默认情况下永远排列在主轴的正方向上

### flex容器上的属性
      如何控制主轴是哪一根 以及主轴的方向
      如果控制侧轴是哪一根 以及侧轴的方向
        flex-flow : row no-wrap
        如何控制主轴是哪一根 以及 主轴的方向
            flex-direction  row row-reverse column column-reverse
        如何控制侧轴是哪一根 以及 侧轴的方向
            flex-wrap no-wrap wrap wrap-reverse
### 富余空间管理
   只要是align开头的属性一定是与侧轴的富余空间管理有关
        主轴: justify-content
                  flex-start 主轴的正方向
                  flex-end   主轴的反方向
                  center     项目整体的两边
                  space-between 在项目之间
                  space-around  在项目的两边
        侧轴:align-items
                  flex-start 侧轴的正方向
                  flex-end   侧轴的反方向
                  center     项目整体的两边
            align-content
                  flex-start
                  flex-end
                  center
                  space-between
                  space-around
### align-items  vs  align-content
    align-items:分配侧轴富余空间是以行/列为单位
    align-content:是以内容整体为单位
### flex项目上的属性
        order: 控制了项目的排列顺序 order越高排的越靠后
        align-self :  flex-start | flex-end | center
            单个项目侧轴的富余空间管理;
                align-items    : 优先级最低
                align-self     : 优先级中等
                align-content  : 优先级最高(必须配合 flex-wrap来使用  侧轴上必须得有堆砌)
                                          (flex-wrap:no-wrap时,align-content不起作用)
        弹性空间管理(将主轴的富裕空间按比例分配给项目)
            flex-shrink
            flex-grow
            flex-basis
            flex
        在分配空间前 将所有的项目基准值都调为0  flex-basis:0%;

        只要每一个item的flex-grow保持一致 就能实现等分布局? 不是!
        如果flex-grow的值相等的话,只是负责给每一个项目分配一样的空间
### flex项目上的属性:
                order : order越大元素越往后靠(order可以写负值)
                align-self: 单独控制一个项目的侧轴上的富裕空间
                flex-shrink: 收缩因子 开发的时候尽量要避免使用到这个属性!!!(默认值 1)
                flex-grow : 伸展因子
                flex-basis: 分配空间时,每个元素的基准值!!
                flex      : 用来实现等分 等比例布局

                富裕空间管理 是不会给项目去分配空间的;它只会控制富裕空间的位置
                弹性空间管理 按比例将主轴的富裕空间分配到项目上

                flex布局不是万能的!!! 它最大的优势在于处理等分 等比例布局

### 弹性空间管理:
        flex
            相当于是flex-grow &  flex-basis简写
            flex:1  flex-grow:1 flex-basis:0%
            flex这个属性适合 等分 等比例布局!!!
                flex-grow  : 弹性因子 默认值为0
                flex-basis : 如果没有指定flex则 使用width/height代替
                    可用空间 = (容器大小 - 所有相邻项目flex-basis的总和)
                      100   =    400 - (50*6)
                      400   =    400 - 0
                    可扩展空间 = (可用空间/所有相邻项目flex-grow的总和)
                      16.666 =  100 / 6
                      66.666 =  400 / 6
                    每项伸缩大小 = (flex-basis + (可扩展空间 x flex-grow值))
                      50 + 16.666
                      0  + 66.666

        flex-shrink: 收缩因子 默认值为1
            当项目在主轴上占据的空间超过整个容器时(在进行布局设计的时候 最好不好出现当前这种情况)
                flex-shrink才有意义
### flex-shrink-收缩因子的计算
    当容器放不下项目时,会使用到收缩因子
     錯誤的方式
        溢出空间: 110 - 400 : -290
        每一项砍的尺寸： 290/5 = -58
        
     正确的方式
        1.计算收缩因子与基准值乘的总和
            1*200 + 1*4*50 = 400
        2.计算收缩因数
          收缩因数=（项目的收缩因子*flex-basis）/第一步计算总和
            1*200 / 400 = 0.5;
            1* 50 / 400 = 0.125;
        3.移除空间的计算
          移除空间= 项目收缩因数 x 负溢出的空间
            0.5 * -290 = -145
            0.125 * -290 = -36.25
### flex布局中的baseline用的很少,不用花心思去研究

### inline-flex
