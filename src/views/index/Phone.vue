<template>
  <!--手机-->
  <div id="f1">
    <div class="mr-container ">
      <div class="shopTitle ">
        <h4>手机</h4>
        <h3>手机风暴</h3>
        <div class="today-brands ">
          <a href="javascript:void(0)" v-for="item in brands" :key="item">{{item}}</a>
        </div>
        <span class="more ">
          <a href="javascript:void(0)">更多手机<i class="mr-icon-angle-right" style="padding-left:10px ;"></i></a>
        </span>
      </div>
    </div>
    <div class="mr-g mr-g-fixed floodFive ">
      <div class="mr-u-sm-5 mr-u-md-3 text-one list">
        <div class="word">
          <a class="outer" href="javascript:void(0)" v-for="item in cores" :key="item">
            <span class="inner"><b class="text">{{item}}</b></span>
          </a>
        </div>
        <a href="javascript:void(0)">
          <img src="@/assets/images/tel.png" width="100px" height="170px"/>
          <div class="outer-con ">
            <div class="title ">
              免费领30天碎屏险
            </div>
            <div class="sub-title ">
              颜值之星，双摄之星
            </div>
          </div>
        </a>
        <div class="triangle-topright"></div>
      </div>
      <div class="mr-u-sm-7 mr-u-md-5 mr-u-lg-2 text-two">
        <div class="outer-con ">
          <div class="title ">
            荣耀8
          </div>
          <div class="sub-title ">
            ¥5888.00
          </div>
          <i class="mr-icon-shopping-basket mr-icon-md  seprate"></i>
        </div>
        <a href="javascript:void(0)" @click="show"><img src="@/assets/images/phone1.jpg"/></a>
      </div>
      <div class="mr-u-md-2 mr-u-lg-2 text-three sug">
        <div class="outer-con ">
          <div class="title ">
            一加手机
          </div>
          <div class="sub-title ">
            ¥2499.00
          </div>
          <i class="mr-icon-shopping-basket mr-icon-md  seprate"></i>
        </div>
        <a href="javascript:void(0)" @click="show"><img src="@/assets/images/phone2.jpg"></a>
      </div>
      <div class="mr-u-md-2 mr-u-lg-2 text-three big">
        <div class="outer-con ">
          <div class="title ">
            红米
          </div>
          <div class="sub-title ">
            ¥1199.00
          </div>
          <i class="mr-icon-shopping-basket mr-icon-md  seprate"></i>
        </div>
        <a href="javascript:void(0)" @click="show"><img src="@/assets/images/phone5.jpg"></a>
      </div>
      <div class="mr-u-sm-4 mr-u-md-5 mr-u-lg-4 text-five">
        <div class="outer-con ">
          <div class="title ">
            LG G5
          </div>
          <div class="sub-title ">
            ¥2999.00
          </div>
          <i class="mr-icon-shopping-basket mr-icon-md  seprate"></i>
        </div>
        <a href="javascript:void(0)" @click="show"><img src="@/assets/images/phone3.jpg"></a>
      </div>
      <div class="mr-u-sm-4 mr-u-md-2 mr-u-lg-2 text-six">
        <div class="outer-con ">
          <div class="title ">
            苹果4s手机
          </div>
          <div class="sub-title ">
            ¥2099.00
          </div>
          <i class="mr-icon-shopping-basket mr-icon-md  seprate"></i>
        </div>
        <a href="javascript:void(0)" @click="show"><img src="@/assets/images/phone4.jpg"></a>
      </div>
      <div class="mr-u-sm-4 mr-u-md-2 mr-u-lg-4 text-six big">
        <div class="outer-con ">
          <div class="title ">
            魅族 魅蓝
          </div>
          <div class="sub-title ">
            ¥999.00
          </div>
          <i class="mr-icon-shopping-basket mr-icon-md  seprate"></i>
        </div>
        <a href="javascript:void(0)" @click="show"><img src="@/assets/images/phone5.jpg"></a>
      </div>
    </div>
    <div class="clear "></div>
  </div>
</template>
<script>
  export default {
    name: 'phone',
    data: function(){
      return {
        //手机品牌数组
        brands: ['小米','荣耀','乐视','魅族','联想','OPPO'],
        //手机核数数组
        cores: ['十核','八核','双四核','四核','双核','单核']
      }
    },
    methods: {
      show: function () {
        this.$router.push({name:'shopinfo'});//跳转到商品详情页面
      }
    }
  }
</script>
