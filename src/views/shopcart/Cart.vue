<template>
  <div>
      <div v-if="list.length>0">
    <div class="main">
      <div class="goods" v-for="(item,index) in list" :key="index">
        <span class="check"><input type="checkbox" @click="selectGoods(index)" :checked="item.isSelect"> </span>
        <span class="name">
			<img :src="item.img">
			{{item.name}}
		</span>
        <span class="unitPrice">{{item.unitPrice | formatPrice}}</span>
        <span class="num">
            <span @click="reduce(index)" :class="{off:item.num==1}">-</span>
            {{item.num}}
            <span @click="add(index)">+</span>
        </span>
        <span class="unitTotalPrice">{{item.unitPrice * item.num | formatPrice}}</span>
        <span class="operation">
            <a @click="remove(index)">删除</a>
        </span>
      </div>
    </div>
    <div class="info">
      <span><input type="checkbox" @click="selectAll" :checked="isSelectAll"> 全选</span>
        <a @click="emptyCar">清空购物车</a>
      <span>已选商品<span class="totalNum">{{totalNum}}</span> 件</span>
      <span>合计:<span class="totalPrice">¥{{totalPrice | formatPrice}}</span></span>
      <span @click="show('pay')">去结算</span>
    </div>
      </div>
      <div class="empty" v-else>
          <img src="@/assets/images/shopcar.png">
          购物车内暂时没有商品，<a @click="show('home')">去购物></a>
      </div>
  </div>
</template>

<script>
  import { mapState,mapActions } from 'vuex'//引入mapState和mapActions
  export default{
    data: function () {
      return {
        isSelectAll : false //默认未全选
      }
    },
    mounted: function(){
        this.isSelectAll = true;//全选
        for(var i = 0;i < this.list.length; i++){
            //有一个商品未选中即取消全选
            if(this.list[i].isSelect == false){
                this.isSelectAll=false;
            }
        }
    },
    filters: {
      formatPrice : function(value){
        return value.toFixed(2);//保留两位小数
      }
    },
    computed : {
        ...mapState([
            'list'	//this.list映射为this.$store.state.list
        ]),
        totalNum : function(){ //计算商品件数
        var totalNum = 0;
        this.list.forEach(function(item){
          if(item.isSelect){
            totalNum+=1;
          }
        });
        return totalNum;
      },
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
    methods : {
        ...mapActions({
            reduce: 'reduceAction',//减少商品个数
            add: 'addAction',//增加商品个数
            remove: 'removeGoodsAction',//移除商品
            selectGoodsAction: 'selectGoodsAction',//选择商品
            selectAllAction: 'selectAllAction',//全选商品
            emptyCarAction: 'emptyCarAction'//清空购物车
        }),
      selectGoods : function(index){ //选择商品
          var goods = this.list[index];
          goods.isSelect = !goods.isSelect;
          this.isSelectAll = true;
          for(var i = 0;i < this.list.length; i++){
              if(this.list[i].isSelect == false){
                  this.isSelectAll=false;
              }
          }
          this.selectGoodsAction({
              index: index,
              bool: goods.isSelect
          });

      },
      selectAll : function(){ //全选或全不选
        this.isSelectAll = !this.isSelectAll;
        this.selectAllAction(this.isSelectAll);
      },
        emptyCar: function(){//清空购物车
          if(confirm('确定要清空购物车吗？')){
              this.emptyCarAction();
          }
        },
      show: function (value) {
          if(value == 'home'){
              this.$router.push({name:'home'});//跳转到主页
          }else{
              if(this.totalNum==0){
                  alert('请至少选择一件商品！');
                  return false;
              }
              this.$router.push({name:'pay'});//跳转到支付页面
          }
      }
    }
  }
</script>
<style src="@/assets/css/style.css" scoped></style>
<style scoped>
    .empty{
        width: 360px;
        margin: 50px auto;
    }
    .empty img{
        width: 100px;
    }
    .empty a{
        color: #0a6999;
        cursor: pointer;
    }
</style>
