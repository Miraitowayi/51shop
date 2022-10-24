<template>
  <div class="concent">
    <div class="paycont">
      <Address/><Logistics/><Payment/><Order/><Bottom/>
    </div>
  </div>
</template>

<script>
  //引入组件
  import Address from '@/views/pay/Address'
  import Logistics from '@/views/pay/Logistics'
  import Payment from '@/views/pay/Payment'
  import Order from '@/views/pay/Order'
  import Bottom from '@/views/pay/Bottom'
  export default {
    name : 'home',
    components : {
      Address,
      Logistics,
      Payment,
      Order,
      Bottom
    }
  }
</script>
<style src="@/assets/css/cartstyle.css" scoped></style>
<style src="@/assets/css/jsstyle.css" scoped></style>
