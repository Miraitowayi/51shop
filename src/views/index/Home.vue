<template>
  <div>
    <NavMenu/><Banner/><shop-main/><NavCir/><Footer/>
  </div>
</template>

<script>
// @是/src的别名
import NavMenu from '@/views/index/NavMenu'
import Banner from '@/views/index/Banner'
import ShopMain from '@/views/index/ShopMain'
import NavCir from '@/views/index/NavCir'
import Footer from '@/components/Footer'

export default {
  name: 'home',
  components: {
    NavMenu,
    Banner,
    ShopMain,
    NavCir,
    Footer
  }
}
</script>
