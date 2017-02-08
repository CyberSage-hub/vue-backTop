# vue-backTop
vue回到顶部
>1.出现时机：当商品列表滑动一屏后，出现

>2.消失时机：当向上滑动后商品列表内容不足一屏幕后，消失

```javascript
import Backtop from '../components/Backtop.vue'
export default {
  components:{
      Backtop
  }
}
```
>在需要插入该组件的地方插入```<backtop></backtop>```即可
