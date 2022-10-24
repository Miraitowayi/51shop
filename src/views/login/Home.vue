<template>
  <div>
  <div class="login-banner">
    <div class="login-main">
      <div class="login-banner-bg"><span></span><img src="@/assets/images/big.png"/></div>
      <div class="login-box">
        <h3 class="title">登录</h3>
        <div class="clear"></div>
        <div class="login-form">
          <form>
            <div class="user-name">
              <label for="user"><i class="mr-icon-user"></i></label>
              <input type="text" v-model="user" id="user" placeholder="邮箱/手机/用户名">
            </div>
            <div class="user-pass">
              <label for="password"><i class="mr-icon-lock"></i></label>
              <input type="password" v-model="password" id="password" placeholder="请输入密码">
            </div>
          </form>
        </div>
        <div class="login-links">
          <label for="remember-me"><input id="remember-me" type="checkbox">记住密码</label>
          <a href="javascript:void(0)" @click="show" class="mr-fr">注册</a>
          <br/>
        </div>
        <div class="mr-cf">
          <input type="submit" name="" value="登 录" @click="login" class="mr-btn mr-btn-primary mr-btn-sm">
        </div>
        <div class="partner">
          <h3>合作账号</h3>
          <div class="mr-btn-group">
            <li><a href="javascript:void(0)"><i class="mr-icon-qq mr-icon-sm"></i><span>QQ登录</span></a></li>
            <li><a href="javascript:void(0)"><i class="mr-icon-weibo mr-icon-sm"></i><span>微博登录</span> </a></li>
            <li><a href="javascript:void(0)"><i class="mr-icon-weixin mr-icon-sm"></i><span>微信登录</span> </a></li>
          </div>
        </div>
      </div>
    </div>
  </div>
  <Bottom/>
  </div>
</template>

<script>
  import {mapActions} from 'vuex'//引入mapActions
  import Bottom from '@/views/login/Bottom'//引入组件
  export default {
    name : 'home',
    components : {
      Bottom//注册组件
    },
    data: function(){
      return {
        user:null,//用户名
        password:null//密码
      }
    },
    methods: {
      ...mapActions([
        'loginAction'//this.loginAction()映射为this.$store.dispatch('loginAction')
      ]),
      login: function () {
        var user=this.user;           //获取用户名
        var password=this.password;  //获取密码
        if(user == null){
          alert('请输入用户名！');
          return false;
        }
        if(password == null){
          alert('请输入密码！');
          return false;
        }
        if(user!=='mr' || password!=='mrsoft' ){
          alert('您输入的账户或密码错误！');
          return false;
        }else{
          alert('登录成功！');
          this.loginAction(user);//触发action并传递用户名
          this.$router.push({name:'home'});//跳转到主页
        }
      },
      show: function () {
        this.$router.push({name:'register'});//跳转到注册页面
      }
    }
  }
</script>
<style src="@/assets/css/login.css" scoped></style>

