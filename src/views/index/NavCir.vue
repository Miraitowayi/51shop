<template>
  <!--手机端导航-->
  <div class="navCir">
    <li class="active"><a href="javascript:void(0)" @click="show('home')"><i class="mr-icon-home "></i>首页</a></li>
    <li><a href="javascript:void(0)" @click="show('shopinfo')"><i class="mr-icon-list"></i>商品</a></li>
    <li><a href="javascript:void(0)" @click="show('shopcart')"><i class="mr-icon-shopping-basket"></i>购物车</a></li>
    <li><a href="javascript:void(0)" @click="show('login')"><i class="mr-icon-user"></i>我的</a></li>
  </div>
</template>
<script>
  export default {
    name: 'navcir',
    methods: {
      show: function (value) {
        this.$router.push({name:value});
      }
    }
  }
</script>
