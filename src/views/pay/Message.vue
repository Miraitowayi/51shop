<template>
  <div>
    <div class="pay-total">
      <!--留言-->
      <div class="order-extra">
        <div class="order-user-info">
          <div id="holyshit257" class="memo">
            <label>买家留言：</label>
            <input type="text" title="选填,对本次交易的说明（建议填写已经和卖家达成一致的说明）" placeholder="选填,建议填写和卖家达成一致的说明"
                   class="memo-input J_MakePoint c2c-text-default memo-close">

            <div class="msg hidden J-msg">
              <p class="error">最多输入500个字符</p>
            </div>
          </div>
        </div>

      </div>
      <!--优惠券 -->
      <div class="buy-agio">
        <li class="td td-coupon">

          <span class="coupon-title">优惠券</span>
          <select data-mr-selected v-model="discount">
            <option value="8">
              <div class="c-price">
                <strong>￥8</strong>
              </div>
              <div class="c-limit">
                【消费满95元可用】
              </div>
            </option>
            <option value="3" selected>
              <div class="c-price">
                <strong>￥3</strong>
              </div>
              <div class="c-limit">
                【无使用门槛】
              </div>
            </option>
          </select>
        </li>

        <li class="td td-bonus">

          <span class="bonus-title">红包</span>
          <select data-mr-selected v-model="redpacket">
            <option value="10.4">
              <div class="item-info">
                ¥50.00<span>元</span>
              </div>
              <div class="item-remainderprice">
                <span>还剩</span>10.40<span>元</span>
              </div>
            </option>
            <option value="50" selected>
              <div class="item-info">
                ¥50.00<span>元</span>
              </div>
              <div class="item-remainderprice">
                <span>还剩</span>50.00<span>元</span>
              </div>
            </option>
          </select>

        </li>

      </div>
      <div class="clear"></div>
    </div>
    <!--含运费小计 -->
    <div class="buy-point-discharge ">
      <p class="price g_price ">
        合计（含运费） <span>¥</span><em class="pay-sum">{{lastPrice | formatPrice}}</em>
      </p>
    </div>
    <Info :lastPrice="lastPrice"/>
  </div>
</template>
<script>
  import Info from '@/views/pay/Info'
  export default {
    props:['totalPrice'],
    data:function () {
      return {
        discount:3,
        redpacket:50
      }
    },
    components:{
      Info
    },
    filters: {
      formatPrice : function(value){
        return value.toFixed(2);
      }
    },
    computed:{
      lastPrice:function () {
        if(this.totalPrice>=95){
          return this.totalPrice-this.discount-this.redpacket;
        }else if(this.discount==3){
          return this.totalPrice-this.discount-this.redpacket;
        }else{
          return this.totalPrice-this.redpacket;
        }
      }
    }
  }
</script>
<style src="@/assets/css/cartstyle.css" scoped></style>
<style src="@/assets/css/jsstyle.css" scoped></style>
