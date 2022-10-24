<template>
  <div class="introduce">
    <Browse/><Introduce/>
  </div>
</template>

<script>
// @是/src的别名
import Browse from '@/views/shopinfo/Browse'
import Introduce from '@/views/shopinfo/Introduce'

export default {
  name: 'related',
  components: {
    Browse,
    Introduce
  }
}
</script>
<style src="@/assets/css/optstyle.css" scoped></style>
<style src="@/assets/css/infoStyle.css" scoped></style>
