<template>
  <div class="home">
    <el-form ref="ruleForm" :rules="rules" :model="ruleForm" class="formlogin" label-width="80px">
      <h1 class="logintitle">登录界面</h1>
      <el-form-item label="账户" prop="username">
        <el-input  type="text" auto-complete="false" v-model="ruleForm.username" placeholder="请输入账户 "></el-input>
      </el-form-item>
      <el-form-item label="密码" prop="password">
        <el-input  type="password" auto-complete="false" v-model="ruleForm.password" placeholder="请输入密码"></el-input>
      </el-form-item>
      <el-form-item label="验证码" prop="code">
        <el-input  type="text"  auto-complete="false" v-model="ruleForm.code" placeholder="验证码"></el-input>
        <img src="" >
      </el-form-item>
      <el-checkbox v-model="checked" style="margin:20px 0px 20px 260px;">请记住</el-checkbox>
      <el-button type="primary" style="width:100%" @click="submitForm(ruleForm)">登录</el-button>
    </el-form>
  </div>
</template>

<script>

export default {
  name: 'Home',
  data () {
    return {
      ruleForm: {
        username: 'admin',
        password: '123'
      },
      checked: true,
      rules: {
        username: [{ required: true, message: '请输入正确账户', trigger: 'blur' }],
        password: [{ required: true, message: '请输入正确密码', trigger: 'blur' }],
        code: [{ required: true, message: '请输入验证码', trigger: 'blur' }]
      }

    }
  },
  methods: {
    // 登录
    submitForm () {
      this.$refs.ruleForm.validate((valid) => {
        if (!valid) return this.$message.error('请输入完整信息')
        alert('登录成功')
      })
    }
  },
  components: {
  }
}
</script>
<style>
  .formlogin {
    border-radius: 15px;
    background-clip: border-box;
    margin: 180px auto;
    width: 350px;
    padding: 15px 35px 15px 35px;
    /* border: 1px solid #ccc; */
    box-shadow: 0 0 25px #ccc;
  }
  .logintitle{
    margin: 0px 5px 40px auto;
    text-align: center;
  }
  .yanzheng {

  }
</style>
