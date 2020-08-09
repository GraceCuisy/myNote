### 在vue中组件数据传递怎么传都行,但是改数据时子组件不要直接修改
    让数据源头组件自己修改
    vuex中一样的道理
### v-if的使用
    v-if='ok'  ok是变量
    v-if='true'
    v-if="'haha'"   v-if中放常量字符串
### 计算属性computed
    执行时机
      页面(组件)初始化: undefined
      计算属性依赖的数据发生改变 计算属性重新执行

### vuex
    store仓库的数据也是响应式数据

### 关于$nextTick
    await+$nextTick是最好的方案
    $nextTick本身是只有数据改变之后就会触发界面更新, 所以不用再watch监听了
    
    什么时候该用$nextTick 
      和真实DOM相关的操作都应该放到this.nextTick中去
### <templete> 和 <block>