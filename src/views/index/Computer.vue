<template>
  <!--电脑-->
  <div id="f2">
    <div class="mr-container ">
      <div class="shopTitle ">
        <h4>电脑</h4>

        <h3>新年换新机</h3>

        <div class="today-brands ">
          <a href="javascript:void(0)">戴尔</a>
          <a href="javascript:void(0)">清华同方</a>
          <a href="javascript:void(0)">小米 </a>
          <a href="javascript:void(0)">联想</a>
          <a href="javascript:void(0)">惠普</a>
          <a href="javascript:void(0)">三星</a>
        </div>
        <span class="more ">
                                <a href="javascript:void(0)">更多电脑<i class="mr-icon-angle-right" style="padding-left:10px ;"></i></a>
                            </span>
      </div>
    </div>
    <div class="mr-g mr-g-fixed floodFour">
      <div class="mr-u-sm-5 mr-u-md-4 text-one list ">
        <div class="word">
          <a class="outer" href="javascript:void(0)"><span class="inner"><b class="text">CPU</b></span></a>
          <a class="outer" href="javascript:void(0)"><span class="inner"><b class="text">显卡</b></span></a>
          <a class="outer" href="javascript:void(0)"><span class="inner"><b class="text">机箱</b></span></a>
          <a class="outer" href="javascript:void(0)"><span class="inner"><b class="text">键盘</b></span></a>
          <a class="outer" href="javascript:void(0)"><span class="inner"><b class="text">鼠标</b></span></a>
          <a class="outer" href="javascript:void(0)"><span class="inner"><b class="text">U盘</b></span></a>
        </div>
        <a href="javascript:void(0)">
          <div class="outer-con ">
            <div class="title ">
              致敬2016
            </div>
            <div class="sub-title ">
              新春大礼包
            </div>
          </div>
          <img src="@/assets/images/computerArt.png" width="120px" height="200px">
        </a>

        <div class="triangle-topright"></div>
      </div>

      <div class="mr-u-sm-7 mr-u-md-4 text-two sug">
        <div class="outer-con ">
          <div class="title ">
            惠普（HP）笔记本
          </div>
          <div class="sub-title ">
            ¥4999.00
          </div>
          <i class="mr-icon-shopping-basket mr-icon-md seprate"></i>
        </div>
        <a href="javascript:void(0)" @click="show"><img src="@/assets/images/computer1.jpg"></a>
      </div>

      <div class="mr-u-sm-7 mr-u-md-4 text-two">
        <div class="outer-con ">
          <div class="title ">
            罗技蓝牙键盘
          </div>
          <div class="sub-title ">
            ¥179.90
          </div>
          <i class="mr-icon-shopping-basket mr-icon-md  seprate"></i>
        </div>
        <a href="javascript:void(0)" @click="show"><img src="@/assets/images/computer2.jpg"></a>
      </div>


      <div class="mr-u-sm-3 mr-u-md-2 text-three big">
        <div class="outer-con ">
          <div class="title ">
            米奇优盘
          </div>
          <div class="sub-title ">
            ¥39.90
          </div>
          <i class="mr-icon-shopping-basket mr-icon-md  seprate"></i>
        </div>
        <a href="javascript:void(0)" @click="show"><img src="@/assets/images/computer3.jpg"></a>
      </div>

      <div class="mr-u-sm-3 mr-u-md-2 text-three sug">
        <div class="outer-con ">
          <div class="title ">
            优派液晶显示器
          </div>
          <div class="sub-title ">
            ¥699.00
          </div>
          <i class="mr-icon-shopping-basket mr-icon-md  seprate"></i>
        </div>
        <a href="javascript:void(0)" @click="show"><img src="@/assets/images/computer4.jpg"></a>
      </div>

      <div class="mr-u-sm-3 mr-u-md-2 text-three ">
        <div class="outer-con ">
          <div class="title ">
            联想笔记本
          </div>
          <div class="sub-title ">
            ¥6599.00
          </div>
          <i class="mr-icon-shopping-basket mr-icon-md  seprate"></i>
        </div>
        <a href="javascript:void(0)" @click="show"><img src="@/assets/images/computer5.jpg"></a>
      </div>

      <div class="mr-u-sm-3 mr-u-md-2 text-three last big ">
        <div class="outer-con ">
          <div class="title ">
            LG 航拍器
          </div>
          <div class="sub-title ">
            ¥699.00
          </div>
          <i class="mr-icon-shopping-basket mr-icon-md  seprate"></i>
        </div>
        <a href="javascript:void(0)" @click="show"><img src="@/assets/images/computer6.jpg"></a>
      </div>

    </div>
  </div>
</template>
<script>
  export default {
    name: 'computer',
    methods: {
      show: function () {
        this.$router.push({name:'shopinfo'});
      }
    }
  }
</script>
