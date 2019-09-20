<template>
  <div class="login">
    <!-- 使用elementUI组件 el-card -->
    <el-card class="login-card">
      <div  class="title">
        <img src="../../assets/logo_index.png" alt />
      </div>
      <!-- 表单=>elform包裹 -->
      <!-- 数据检验=>el-form绑定model 绑定rules规则-->
      <el-form ref="myForm" :model="loginForm" :rules="loginRules" style="margin-top:20px">
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
            <el-button @click="login" type="primary"  style="width:100%">登录</el-button>
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
      loginRules: {
        //   决定着校验规则  key(字段名):value(对象数组) => 一个对象就是一个校验规则
        // required 为true 就表示该字段必填 如果不填 就会提示消息
        mobile: [{ required: true, message: '请输入您的手机号' },
          { pattern: /^1[3456789]\d{9}$/, message: '请输入合法的手机号' }],
        code: [{ required: true, message: '请输入您的验证码' },
          { pattern: /^\d{6}$/, message: '验证码为6位数字' }],
        agree: [{ validator: function (rule, value, callBack) {
          // if (value) {
          //   // 正确,勾选了协议
          //   callBack()
          // } else {
          //   // 不对,没勾选协议
          //   callBack(new Error('您必须同意无条件被我们蒙骗'))
          // }
          value ? callBack() : callBack(new Error('您必须无条件被我们蒙骗'))
        } } ]
      } // 登录规则集合对象
      // 自定义形式去校验
    }
  }, // 登陆会的
  methods: {
    login () {
      // 校验整个表单的规则
      // validate是一个方法,=>方法中传入的一个函数
      this.$refs.myForm.validate(function (isOK) {
        if (isOK) {
          console.log('校验成功')
        }
      })
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
