<template>
  <div class="introduceMain">
    <div class="mr-tabs" data-mr-tabs>
      <ul class="mr-avg-sm-3 mr-tabs-nav mr-nav mr-nav-tabs">
        <li id="infoTitle" :class="{'mr-active':current=='Details'}">
          <a @click="current='Details'">
            <span class="index-needs-dt-txt">宝贝详情</span></a>
        </li>

        <li id="commentTitle" :class="{'mr-active':current=='Comment'}">
          <a @click="current='Comment'">
            <span class="index-needs-dt-txt">全部评价</span></a>
        </li>

        <li id="youLikeTitle" :class="{'mr-active':current=='Like'}">
          <a @click="current='Like'">
            <span class="index-needs-dt-txt">猜你喜欢</span></a>
        </li>
      </ul>
      <div class="mr-tabs-bd">
        <component :is="current"></component>
      </div>
    </div>
    <div class="clear"></div>

    <div class="footer ">
      <div class="footer-hd ">
        <p>
          <a href="http://www.mingrisoft.com/" target="_blank">德云学苑</a>
          <b>|</b>
          <a href="javascript:void(0)" @click="show">商城首页</a>
          <b>|</b>
          <a href="javascript:void(0)">支付宝</a>
          <b>|</b>
          <a href="javascript:void(0)">物流</a>
        </p>
      </div>
      <div class="footer-bd ">
        <p>
          <a href="http://www.mingrisoft.com/Index/ServiceCenter/aboutus.html" target="_blank">关于我们</a>
          <a href="javascript:void(0)">合作伙伴</a>
          <a href="javascript:void(0)">联系我们</a>
          <a href="javascript:void(0)">网站地图</a>
          <em>&copy; 2016-2025 mingrisoft.com 版权所有</em> </p>
      </div>
    </div>
  </div>
</template>
<script>
  import Details from '@/views/shopinfo/Details'//引入组件
  import Comment from '@/views/shopinfo/Comment'//引入组件
  import Like from '@/views/shopinfo/Like'//引入组件
  export default {
    name: 'introduce',
    data: function(){
      return {
        current: 'Details'	//当前显示组件
      }
    },
    components: {
      Details,
      Comment,
      Like
    },
    methods: {
      show: function () {
        this.$router.push({name:'home'});//跳转到主页
      }
    }
  }
</script>
<style src="@/assets/css/optstyle.css" scoped></style>
<style src="@/assets/css/infoStyle.css" scoped></style>
