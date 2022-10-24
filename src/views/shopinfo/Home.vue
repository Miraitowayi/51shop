<template>
  <div>
    <b class="line"></b>
      <div class="nav-table">
        <Nav/>
      </div>
    <Info/>
    <Discount/>
    <Related/>
  </div>
</template>

<script>
// @是/src的别名
import Nav from '@/components/Nav'
import Info from '@/views/shopinfo/Info'
import Discount from '@/views/shopinfo/Discount'
import Related from '@/views/shopinfo/Related'

export default {
  name: 'home',
  components: {
    Nav,
    Info,
    Discount,
    Related
  }
}
</script>

