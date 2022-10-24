<template>
  <div>
    <ol class="mr-breadcrumb mr-breadcrumb-slash">
      <li><a href="javascript:void(0)">首页</a></li>
      <li><a href="javascript:void(0)">分类</a></li>
      <li class="mr-active">内容</li>
    </ol>

    <div class="scoll">
      <section class="slider">
        <div class="flexslider">
          <ul class="slides">
            <li>
              <img src="@/assets/images/01.jpg" title="pic">
            </li>
            <li>
              <img src="@/assets/images/02.jpg">
            </li>
            <li>
              <img src="@/assets/images/03.jpg">
            </li>
          </ul>
        </div>
      </section>
    </div>

    <!--放大镜-->

    <div class="item-inform">
      <Enlarge/>

      <div class="clearfixRight">

        <!--规格属性-->
        <!--名称-->
        <div class="tb-detail-hd">
          <h1>
            {{goodsInfo.name}}
          </h1>
        </div>
        <div class="tb-detail-list">
          <!--价格-->
          <div class="tb-detail-price">
            <li class="price iteminfo_price">
              <dt>促销价</dt>
              <dd><em>¥</em><b class="sys_item_price">{{goodsInfo.unitPrice | formatPrice}}</b></dd>
            </li>
            <li class="price iteminfo_mktprice">
              <dt>原价</dt>
              <dd><em>¥</em><b class="sys_item_mktprice">599.00</b></dd>
            </li>
            <div class="clear"></div>
          </div>

          <!--地址-->
          <dl class="iteminfo_parameter freight">
            <dt>配送至</dt>
            <div class="iteminfo_freprice">
              <div class="mr-form-content address">
                <select data-mr-selected>
                  <option value="a">浙江省</option>
                  <option value="b">陕西省</option>
                </select>
                <select data-mr-selected>
                  <option value="a">温州市</option>
                  <option value="b">西京市</option>
                </select>
                <select data-mr-selected>
                  <option value="a">瑞安区</option>
                  <option value="b">广安区</option>
                </select>
              </div>
              <div class="pay-logis">
                快递<b class="sys_item_freprice">10</b>元
              </div>
            </div>
          </dl>
          <div class="clear"></div>

          <!--销量-->
          <ul class="tm-ind-panel">
            <li class="tm-ind-item tm-ind-sellCount canClick">
              <div class="tm-indcon"><span class="tm-label">月销量</span><span class="tm-count">1015</span></div>
            </li>
            <li class="tm-ind-item tm-ind-sumCount canClick">
              <div class="tm-indcon"><span class="tm-label">累计销量</span><span class="tm-count">6015</span></div>
            </li>
            <li class="tm-ind-item tm-ind-reviewCount canClick tm-line3">
              <div class="tm-indcon"><span class="tm-label">累计评价</span><span class="tm-count">640</span></div>
            </li>
          </ul>
          <div class="clear"></div>

          <!--各种规格-->
          <dl class="iteminfo_parameter sys_item_specpara">
            <dt class="theme-login">
              <div class="cart-title">可选规格<span class="mr-icon-angle-right"></span></div>
            </dt>
            <dd>
              <!--操作页面-->

              <div class="theme-popover-mask"></div>

              <div class="theme-popover">
                <div class="theme-span"></div>
                <div class="theme-poptit">
                  <a href="javascript:;" title="关闭" class="close">×</a>
                </div>
                <div class="theme-popbod dform">
                  <form class="theme-signin" name="loginform" action="" method="post">

                    <div class="theme-signin-left">

                      <div class="theme-options">
                        <div class="cart-title">颜色</div>
                        <ul>
                          <li class="sku-line selected">荣耀金<i></i></li>
                          <li class="sku-line">冰河银<i></i></li>
                          <li class="sku-line">雅典灰<i></i></li>
                        </ul>
                      </div>
                      <div class="theme-options">
                        <div class="cart-title">套装</div>
                        <ul>
                          <li class="sku-line selected">保护套装<i></i></li>
                          <li class="sku-line">原厂电源<i></i></li>
                          <li class="sku-line">存储套装<i></i></li>
                        </ul>
                      </div>
                      <div class="theme-options">
                        <div class="cart-title number">数量</div>
            <dd>
              <input id="min" class="mr-btn mr-btn-default" @click="reduce" type="button" value="-"/>
              <input id="text_box" type="text" value="1" v-model="number" style="width:30px;"/>
              <input id="add" class="mr-btn mr-btn-default" @click="add" type="button" value="+"/>
              <span id="Stock" class="tb-hidden">库存<span class="stock">1000</span>件</span>
            </dd>

        </div>
        <div class="clear"></div>

        <div class="btn-op">
          <div class="btn mr-btn mr-btn-warning">确认</div>
          <div class="btn close mr-btn mr-btn-warning">取消</div>
        </div>
      </div>
      <div class="theme-signin-right">
        <div class="img-info">
          <img src=""/>
        </div>
        <div class="text-info">
          <span class="J_Price price-now">¥39.00</span>
          <span id="Stock" class="tb-hidden">库存<span class="stock">1000</span>件</span>
        </div>
      </div>

      </form>
    </div>
  </div>

  </dd>
  </dl>
  <div class="clear"></div>
  <!--活动	-->
  <div class="shopPromotion gold">
    <div class="hot">
      <dt class="tb-metatit">店铺优惠</dt>
      <div class="gold-list">
        <p>购物满2件打8折，满3件7折</p>
      </div>
    </div>
    <div class="clear"></div>
  </div>
  </div>

  <div class="pay">
    <div class="pay-opt">
      <a href="index.html"><span class="mr-icon-home mr-icon-fw">首页</span></a>
      <a><span class="mr-icon-heart mr-icon-fw">收藏</span></a>

    </div>
    <li>
      <div class="clearfix tb-btn tb-btn-buy theme-login">
        <a id="LikBuy" title="点此按钮到下一步确认购买信息" @click="show">立即购买</a>
      </div>
    </li>
    <li>
      <div class="clearfix tb-btn tb-btn-basket theme-login">
        <a id="LikBasket" title="加入购物车" @click="show"><i></i>加入购物车</a>
      </div>
    </li>
  </div>

  </div>

  <div class="clear"></div>

  </div>
  </div>
</template>

<script>
  import Enlarge from '@/views/shopinfo/Enlarge'
  import {mapState,mapActions} from 'vuex'//引入mapState和mapActions
  export default {
    components: {
      Enlarge
    },
    data: function(){
      return {
        number: 1,//商品数量
        goodsInfo: {//商品基本信息
          img : require("@/assets/images/honor.jpg"),
          name : "华为 荣耀 畅玩4X 白色 移动4G手机",
          num : 0,
          unitPrice : 499,
          isSelect : true
        }
      }
    },
    computed: {
      ...mapState([
              'user'//this.user映射为this.$store.state.user
      ])
    },
      watch: {
        number: function (newVal,oldVal) {
            if(isNaN(newVal) || newVal == 0){//输入的是非数字或0
                this.number = oldVal;//数量为原来的值
            }
        }
      },
    filters: {
      formatPrice : function(value){
        return value.toFixed(2);//保留两位小数
      }
    },
    methods: {
      ...mapActions([
              'getListAction'//this.getListAction()映射为this.$store.dispatch('getListAction')
      ]),
      show: function () {
          if(this.user == null){
              alert('亲，请登录！');
              this.$router.push({name:'login'});//跳转到登录页面
          }else{
            this.getListAction({//执行方法并传递参数
              goodsInfo: this.goodsInfo,
              number: parseInt(this.number)
            });
              this.$router.push({name:'shopcart'});//跳转到购物车页面
          }
      },
      reduce: function () {
        if(this.number >= 2){
          this.number--;//商品数量减1
        }

      },
      add: function () {
        this.number++;//商品数量加1
      }
    }
  }
</script>
<style src="@/assets/css/optstyle.css" scoped></style>
<style src="@/assets/css/infoStyle.css" scoped></style>
