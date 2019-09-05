# vant-vue




<van-cell-group v-if="!wxvis">
         <van-cell id="money" class="data_xq_days" title="还款金额"  v-model="repayment.repaycount+ ' 元'"/>
        <!-- <van-cell class="data_xq_days" @click="getsocal" title="支付方式" is-link v-model="repayment.repaycard"/> -->
		<div v-show="show" style="position: fixed;top:0;left:0;right:0;bottom:0;background: rgba(0,0,0,.4);z-index: 99">
        <!-- <van-popup v-model="show" position="bottom" :overlay="false">
            <van-picker 
            show-toolbar
            title="支付方式"
            :columns="columns"
            @cancel="onCancel"
            @confirm="onConfirm"
          />
        </van-popup> -->
        
		<van-popup v-model="show" position="bottom" :overlay="false">
			<van-icon @click="closepay" style="position:absolute;top:5px;right:16px" size=1.5em name="close" />
			<van-col span="24" style="padding: 12px 0;">选择支付方式</van-col>
			<div>
				<div v-show="loadvis" style="position: absolute;width: 100%;top:50px;left: 0;right: 0;bottom: 0;z-index: 99;background: #fff;text-align: center;">
					<van-loading style="margin:30px auto 20px;"  size="24px" vertical>支付中...</van-loading>
					<span style="font-size: 12px;color: #999;">正在支付中</span>
				</div>
				<van-col span="18">
					<van-cell @click="pays('1')" title="支付宝支付" v-bind:icon="alipimg" />
				</van-col>
				<van-col span="6">
				  <van-radio-group @change="radioclick" v-model="radio">
				    <van-radio name="1"></van-radio>
				  </van-radio-group>
				</van-col>
				
				
				<van-col span="18" >
					<van-cell @click="pays('2')" title="微信支付" v-bind:icon="wxpimg" />
				</van-col>
				<van-col span="6">
				  <van-radio-group @change="radioclick"  v-model="radio">
				    <van-radio name="2"></van-radio>
				  </van-radio-group>
				</van-col>
				
				
				
				<van-col span="18">
					<van-cell @click="pays('3')" title="线下支付" v-bind:icon="mendp" />
				</van-col>
				<van-col span="6">
				  <van-radio-group @change="radioclick"  v-model="radio">
				    <van-radio name="3"></van-radio>
				  </van-radio-group>
				</van-col>
			</div>
			
		
			
			<van-col span="24" style="padding: 12px 0;">
				<button @click="paymoneyon" style="background: #3e74fc;color: #fff;border-radius: 6px;padding: 8px;width: 80%;margin: auto;border: none;margin: 1em auto;">确认支付</button>
			</van-col>
		   	
		</van-popup>
		</div>
      </van-cell-group>























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
    
    
