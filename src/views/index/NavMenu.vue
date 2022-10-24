<template>
  <div class="shopNav">
    <div class="slideall">
      <Nav/>
      <Menu/>
    </div>
  </div>
</template>

<script>
import Nav from '@/components/Nav';
import Menu from '@/views/index/Menu';
export default {
	name: 'navmenu',
	components: {
      Nav,
      Menu
    }
}
</script>
