<template>
  <el-card class="rebox">
    <div class="useraccount">
      <span>用户账号</span>
      <el-input v-model="ua" style="width: 300px" placeholder="请输入用户账号"/>
      <span style="color:red">*</span>
    </div>

    <div class="username">
      <span>用户名称</span>
      <el-input v-model="un" style="width: 300px" placeholder="请输入用户名"/>
      <span style="color:red">*</span>
    </div>

    <div class="pw">
      <span>用户密码</span>
      <el-input v-model="pw" style="width: 300px" type="password" placeholder="请输入用户密码"/>
      <span style="color:red">*</span>
    </div>

    <div class="pwa">
      <span>确认密码</span>
      <el-input v-model="pwa" style="width: 300px" type="password" placeholder="再次输入密码"/>
      <span style="color:red">*</span>
    </div>

    <div class="phone">
      <span>联系电话</span>
      <el-input v-model="phone" style="width: 300px" placeholder="请输入联系电话"/>
      <span style="color:red">*</span>
    </div>

    <div class="email">
      <span>用户邮箱</span>
      <el-input v-model="email" style="width: 300px" placeholder="请输入用户邮箱"/>
      <span style="color:red">*</span>
    </div>

    <div class="name">
      <span>用户真名</span>
      <el-input v-model="name" style="width: 300px" placeholder="请输入用户真名"/>
      <span style="color:red">*</span>
    </div>

    <div class="identity">
      <span>用户身份</span>
      <el-input v-model="ui" style="width: 300px" placeholder="请输入用户身份"/>
      <span style="color:red">*</span>
    </div>

    <el-button
        @click="register"
        class="in"
        style="margin: 10px auto;
            top: 50vh;
            height: 5vh;
            width: 60vh"
        type="primary"
        color="blue"
        round="true">register
    </el-button>

  </el-card>

</template>

<script setup lang="ts">
import {ref} from 'vue'
import axios from "axios";

let ua = ref('')
let un=ref("")
let pw = ref('')
let pwa = ref('')
let phone=ref("")
let email=ref("")
let name=ref("")
let ui=ref("")

function register() {
  if (pw.value !== pwa.value) return
  axios.post('https://localhost:8080/register',{
    useraccount:ua,
    username: un,
    password: pw,
    phone:phone,
    email:email,
    name:name,
    identity:ui,
  }).then((result) => {
    if (result.data.code === 1)
      console.log('post successful')
    else {
      console.log('post failed')
      console.log(result.data.msg)
    }
  })
}
</script>

<style scoped>
.rebox {
  padding-top: 20px;
  display: flex;
  flex-direction: column; /* 设置主轴为垂直方向 */
  align-items: center; /* 子元素在容器中垂直居中 */
  border-radius: 10px;
  gap: 20px;
  width: 40vw;
  height: 70vh;
  margin-top: 90px;
  position: absolute;
  left: 50%;
  top: 35%;
  transform: translate(-50%, -50%);
}

div {
  margin: 5px auto;
}
span{
  margin-right: 10px;
}
</style>