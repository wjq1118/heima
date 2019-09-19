<template>
  <div class="login">
    <!-- 使用elementUI组件 el-card -->
    <el-card class="login-card">
      <div  class="title">
        <img src="../../assets/logo_index.png" alt />
      </div>
      <!-- 表单=>elform包裹 -->
      <!-- 数据检验=>el-form绑定model 绑定rules规则-->
      <el-form :model="loginForm" :rules="loginRules" style="margin-top:20px">
          <!-- form-item  prop属性  绑定下面表单组件的字段名 -->
        <el-form-item prop="mobile">
          <!-- 手机号 -->
          <el-input v-model="loginForm.mobile" placeholder="请输入手机号"></el-input>
        </el-form-item>
        <el-form-item prop="code">
          <!-- 验证码 -->
          <el-input v-model="loginForm.code" placeholder="请输入验证码" style="width:65%"></el-input>
          <!-- 发送验证码 -->
          <el-button style="float:right ">发送验证码</el-button>
        </el-form-item>
        <el-form-item prop="agree">
          <el-checkbox v-model="loginForm.agree">我已阅读并同意用户协议和隐私条款</el-checkbox>
        </el-form-item>
        <el-form-item>
            <!-- 登录按钮 -->
            <el-button type="primary"  style="width:100%">登录</el-button>
        </el-form-item>
      </el-form>
    </el-card>
  </div>
</template>

<script>
export default {
  data () {
    return {
      //    表单数据  是一个对象
      loginForm: {
        mobile: '', // 手机号
        code: '', // 验证码
        agree: false // 是否同意协议
      },
      loginRules: {} // 登陆规则集合对象
    }
  }
}
</script>

<style lang="less" scoped>
// 如果要在组件样式中写less,就要给一个lang属性   lang='less'
.login {
  background-image: url(../../assets/login_bg.jpg);
  height: 100vh;
  background-size: cover;
  display: flex;
  justify-content: center;
  align-items: center;
  .login-card {
    width: 440px;
    height: 340px;
    .title {
      text-align: center;
      img {
        height: 45px;
      }
    }
  }
}
</style>
