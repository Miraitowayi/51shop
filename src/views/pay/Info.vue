<template>
  <!--信息 -->
  <div class="order-go clearfix">
    <div class="pay-confirm clearfix">
      <div class="box">
        <div tabindex="0" id="holyshit267" class="realPay"><em class="t">实付款：</em>
          <span class="price g_price ">
            <span>¥</span>
            <em class="style-large-bold-red " id="J_ActualFee">{{lastPrice | formatPrice}}</em>
          </span>
        </div>
        <div id="holyshit268" class="pay-address">
          <p class="buy-footer-address">
            <span class="buy-line-title buy-line-title-type">寄送至：</span>
            <span class="buy--address-detail">
              <span class="province">陕西</span>省
              <span class="city">西京</span>市
              <span class="dist">广安</span>区
              <span class="street">星云广场财富领域1198室</span>
            </span>
          </p>
          <p class="buy-footer-address">
            <span class="buy-line-title">收货人：</span>
            <span class="buy-address-detail">
              <span class="buy-user">李丹 </span>
              <span class="buy-phone">1586699****</span>
            </span>
          </p>
        </div>
      </div>
      <div id="holyshit269" class="submitOrder">
        <div class="go-btn-wrap">
          <a id="J_Go" class="btn-go" tabindex="0" title="点击此按钮，提交订单" @click="show">提交订单</a>
        </div>
      </div>
      <div class="clear"></div>
    </div>
  </div>
</template>
<script>
  import {mapActions} from 'vuex'//引入mapActions
  export default {
    props:['lastPrice'],//父组件传递的数据
    methods: {
        ...mapActions({
          emptyCar: 'emptyCarAction'//this.emptyCar()映射为this.$store.dispatch('emptyCarAction')
        }),
      show: function () {
          this.emptyCar();//执行清空购物车操作
        this.$router.push({name:'home'});//跳转到主页
      }
    },
    filters: {
      formatPrice : function(value){
        return value.toFixed(2);//保留两位小数
      }
    }
  }
</script>
<style src="@/assets/css/cartstyle.css" scoped></style>
<style src="@/assets/css/jsstyle.css" scoped></style>
