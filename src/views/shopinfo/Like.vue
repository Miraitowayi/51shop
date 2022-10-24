<template>
  <div id="youLike" class="mr-tab-panel">
    <div class="like">
      <ul class="mr-avg-sm-2 mr-avg-md-3 mr-avg-lg-4 boxes">
        <li>
          <div class="i-pic limit">
            <img src="@/assets/images/shopcartImg.jpg">
            <p>华为 荣耀 畅玩4X 白色 移动4G手机 双卡双待</p>
            <p class="price fl">
              <b>¥</b>
              <strong>498.00</strong>
            </p>
          </div>
        </li>
        <li>
          <div class="i-pic limit">
            <img src="@/assets/images/shopcartImg.jpg">
            <p>华为 荣耀 畅玩4X 白色 移动4G手机 双卡双待</p>
            <p class="price fl">
              <b>¥</b>
              <strong>498.00</strong>
            </p>
          </div>
        </li>
        <li>
          <div class="i-pic limit">
            <img src="@/assets/images/shopcartImg.jpg">
            <p>华为 荣耀 畅玩4X 白色 移动4G手机 双卡双待</p>
            <p class="price fl">
              <b>¥</b>
              <strong>498.00</strong>
            </p>
          </div>
        </li>
        <li>
          <div class="i-pic limit">
            <img src="@/assets/images/shopcartImg.jpg">
            <p>华为 荣耀 畅玩4X 白色 移动4G手机 双卡双待</p>
            <p class="price fl">
              <b>¥</b>
              <strong>498.00</strong>
            </p>
          </div>
        </li>
        <li>
          <div class="i-pic limit">
            <img src="@/assets/images/shopcartImg.jpg">
            <p>华为 荣耀 畅玩4X 白色 移动4G手机 双卡双待</p>
            <p class="price fl">
              <b>¥</b>
              <strong>498.00</strong>
            </p>
          </div>
        </li>
        <li>
          <div class="i-pic limit">
            <img src="@/assets/images/shopcartImg.jpg">
            <p>华为 荣耀 畅玩4X 白色 移动4G手机 双卡双待</p>
            <p class="price fl">
              <b>¥</b>
              <strong>498.00</strong>
            </p>
          </div>
        </li>
        <li>
          <div class="i-pic limit">
            <img src="@/assets/images/shopcartImg.jpg">
            <p>华为 荣耀 畅玩4X 白色 移动4G手机 双卡双待</p>
            <p class="price fl">
              <b>¥</b>
              <strong>498.00</strong>
            </p>
          </div>
        </li>
        <li>
          <div class="i-pic limit">
            <img src="@/assets/images/shopcartImg.jpg">
            <p>华为 荣耀 畅玩4X 白色 移动4G手机 双卡双待</p>
            <p class="price fl">
              <b>¥</b>
              <strong>498.00</strong>
            </p>
          </div>
        </li>
      </ul>
    </div>
    <div class="clear"></div>
    <!--分页 -->
    <ul class="mr-pagination mr-pagination-right">
      <li :class="{'mr-disabled':curentPage==1}" @click="jump(curentPage-1)"><a href="javascript:void(0)">&laquo;</a></li>
      <li :class="{'mr-active':curentPage==n}" v-for="n in pages" :key="n" @click="jump(n)">
        <a href="javascript:void(0)">{{n}}</a>
      </li>
      <li :class="{'mr-disabled':curentPage==pages}" @click="jump(curentPage+1)"><a href="javascript:void(0)">&raquo;</a></li>
    </ul>
    <div class="clear"></div>
  </div>
</template>
<script>
  export default {
    data: function () {
      return {
        items: [],
        eachNum: 4,//每页显示个数
        curentPage: 1//当前页数
      }
    },
    mounted: function(){
      this.items = document.querySelectorAll('.like li');//获取所有元素
      for(var i = 0; i < this.items.length; i++){
        if(i < this.eachNum){
          this.items[i].style.display = 'block';//显示第一页内容
        }else{
          this.items[i].style.display = 'none';//隐藏其他页内容
        }
      }
    },
    computed: {
      count: function () {
        return this.items.length;//元素总数
      },
      pages: function () {
        return Math.ceil(this.count/this.eachNum);//总页数
      }
    },
    methods: {
      jump: function (n) {
        this.curentPage = n;
        if(this.curentPage < 1){
          this.curentPage = 1;//页数最小值
        }
        if(this.curentPage > this.pages){
          this.curentPage = this.pages;//页数最大值
        }
        for(var i = 0; i < this.items.length; i++){
          this.items[i].style.display = 'none';//隐藏所有元素
        }
        var start = (this.curentPage - 1) * this.eachNum;//每页第一个元素索引
        var end = start + this.eachNum;//每页最后一个元素索引
        end = end > this.count ? this.count : end;//尾页最后一个元素索引
        for(var j = start; j < end; j++){
          this.items[j].style.display = 'block';//当前页元素显示
        }
      }
    }
  }
</script>
<style src="@/assets/css/optstyle.css" scoped></style>
<style src="@/assets/css/infoStyle.css" scoped></style>
