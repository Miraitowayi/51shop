<template>
  <div id="app">
    <Top/>
    <router-view/>
  </div>
</template>
<script>
  import Top from '@/components/Top'
  export default {
    name: 'app',
    components: {
      Top
    }
  }
</script>
<style lang="scss">
@import "./assets/css/basic.css";
@import "./assets/css/admin.css";
@import "./assets/css/demo.css";
@import "./assets/css/hmstyle.css";
</style>
