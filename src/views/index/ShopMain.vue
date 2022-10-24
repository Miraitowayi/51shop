<template>
  <div class="shopMainbg">
    <div class="shopMain" id="shopmain">
      <Recommend/><Activity/><Phone/><Computer/>
    </div>
  </div>
</template>

<script>
// @是/src的别名
import Recommend from '@/views/index/Recommend'
import Activity from '@/views/index/Activity'
import Phone from '@/views/index/Phone'
import Computer from '@/views/index/Computer'

export default {
  name: 'shopmain',
  components: {
    Recommend,
    Activity,
    Phone,
    Computer
  }
}
</script>
