<template>
  <!--订单 -->
    <div>
  <div class="concent">
    <div id="payTable">
      <h3>确认订单信息</h3>
      <div class="cart-table-th">
        <div class="wp">
          <div class="th th-item">
            <div class="td-inner">商品信息</div>
          </div>
          <div class="th th-price">
            <div class="td-inner">单价</div>
          </div>
          <div class="th th-amount">
            <div class="td-inner">数量</div>
          </div>
          <div class="th th-sum">
            <div class="td-inner">金额</div>
          </div>
          <div class="th th-oplist">
            <div class="td-inner">配送方式</div>
          </div>
        </div>
      </div>
      <div class="clear"></div>
      <div class="main">
        <div class="goods" v-for="(item,index) in list" :key="index">
          <span class="name">
              <img :src="item.img">
              {{item.name}}
          </span>
          <span class="unitPrice">{{item.unitPrice | formatPrice}}</span>
          <span class="num">
              {{item.num}}
          </span>
          <span class="unitTotalPrice">{{item.unitPrice * item.num | formatPrice}}</span>
            <span class="pay-logis">
                快递送货
            </span>
        </div>
      </div>
    </div>
  </div>
    <Message :totalPrice="totalPrice"/>
    </div>
</template>
<script>
  import {mapGetters} from 'vuex'//引入mapGetters
  import Message from '@/views/pay/Message'//引入组件
  export default {
    components:{
      Message//注册组件
    },
    computed: {
      ...mapGetters([
              'list'//this.list映射为this.$store.getters.list
      ]),
      totalPrice : function(){ //计算商品总价
        var totalPrice = 0;
        this.list.forEach(function(item){
          if(item.isSelect){
            totalPrice += item.num*item.unitPrice;
          }
        });
        return totalPrice;
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
<style src="@/assets/css/orderstyle.css" scoped></style>
