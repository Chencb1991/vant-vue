# vant-vue

> tabbar

```
<van-tabbar @change="change(active)" fixed v-model="active" active-color="#575BFF">
      <van-tabbar-item to="/mains">
        <span>首页</span>
        <img
          slot="icon"
          slot-scope="props"
          :src="props.active ? icon.active : icon.normal"
        >
      </van-tabbar-item>
      <van-tabbar-item  to="/loan">贷款
         <img
          slot="icon"
          slot-scope="props"
          :src="props.active ? icon1.active : icon1.normal"
        >
      </van-tabbar-item>
      <van-tabbar-item icon="setting-o"  to="/user">我的
        <img
          slot="icon"
          slot-scope="props"
          :src="props.active ? icon2.active : icon2.normal"
        >
      </van-tabbar-item>
    </van-tabbar>
    
    
    export default {
   data() {
    return {
      active: null,
      tabs:[0,1,2],
      icon: {
        normal: require('../assets/2.png'),
        active: require('../assets/22.png'),
      },
       icon1: {
        normal: require('../assets/1.png'),
        active: require('../assets/11.png'),
      },
       icon2: {
        normal: require('../assets/3.png'),
        active: require('../assets/33.png'),
      }
    }
  }
  }
    ```
    
    > 自定义弹出框
    ```
    <van-dialog v-model="show"  title='确认消息' show-cancel-button
        message= '您确定要退出当前账号吗？' :before-close="beforeClose">
      </van-dialog>
      
      
   ```
    
    
