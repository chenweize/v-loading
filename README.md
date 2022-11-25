# v-loading
vue全局loading指令
### 用法：
在main.js引入
```
import directiveLoading from '@/components/loading' // 自定义loading指令
Vue.use(directiveLoading)
```
在对应标签中声明指令v-loading
```
<div v-loading="true"></div>
```
