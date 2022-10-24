<template>
  <div class="box">
    <div class="title">
      <span class="check">选择</span>
      <span class="name">商品信息</span>
      <span class="unitPrice">单价</span>
      <span class="num">数量</span>
      <span class="unitTotalPrice">金额</span>
      <span class="operation">操作</span>
    </div>
    <Cart/><Bottom/>
  </div>
</template>

<script>
  //引入组件
  import Cart from '@/views/shopcart/Cart'
  import Bottom from '@/views/shopcart/Bottom'
  export default {
    name : 'home',
    components : {
      Cart,
      Bottom
    }
  }
</script>
<style src="@/assets/css/style.css" scoped></style>

