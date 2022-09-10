<template>
  <div class="login">
    <div class="logo">
      <img src="../assets/logo.jpg" alt="login image">
    </div>
    <!-- 手机号 -->
    <InputGroup 
      type="number"
      v-model="phone"
      placeholder="手机号"
      :btnTitle="btnTitle"
      :disabled="disabled"
      :error="errors.phone"
    />
    <!-- 验证码 -->
    <InputGroup type="number" v-model="verifyCode" placeholder="验证码" :error="errors.code" />

    <!-- 用户服务协议 -->
    <div class="login_des">
      <p>
      新用户登录即自动注册，表示同意
      <span>《用户服务协议》</span>
      </p>
    </div>
    <!-- 登录按钮 -->
    <div class="login_btn">
      <button>登录</button>
    </div>
  </div>
</template>

<script>
import InputGroup from '../components/InputGroup'
export default {
  name: "login",
  components: {
    InputGroup
  },
  data() {
    return {
      phone: '',
      verifyCode: '',
      errors: {},
      btnTitle: '获取验证码',
      disabled: false
    }
  }
}
</script>

<style scoped>
.login {
  width: 100%;
  height: 100%;
  padding: 30px;
  box-sizing: border-box;
  background: #fff;
}
.logo {
  text-align: center;
}
.logo img {
  width:150px;
}
.text_group,
.login_des,
.login_btn {
  margin-top: 20px;
}
.login_des {
  color: #aaa;
  line-height: 22px;
}
.login_des span {
  color: #4d90fe;
}
.login_btn button {
  width: 100%;
  height: 40px;
  background-color: #48ca38;
  border-radius: 4px;
  color: white;
  font-size: 14px;
  border: none;
  outline: none;
}
.login_btn button[disabled] {
  background-color: #8bda81;
}
</style>