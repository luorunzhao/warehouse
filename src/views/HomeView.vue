<script setup lang="ts">
import {useRouter} from "vue-router";

let router = useRouter()

function login(){

}
function toRegister() {
  router.push('/register')
}
</script>

<template>
  <div id="out">
    <div id="title" class="in">
      Welcome Use This System!
    </div>
    <div id="context" class="in">
      Please choose operation.
    </div>
    <el-button
        class="in"
        @click="login"
        style="margin: 10px auto;
            top: 50vh;
            height: 5vh;
            width: 60vh"
        type="primary"
        color="blue"
        round="true">login in</el-button>
    <el-button
        class="in"
        @click="toRegister"
        style="margin: 10px auto;
            top: 60vh;
            height: 5vh;
            width: 60vh"
        round="true">register</el-button>
  </div>
</template>

<style scoped>
.title{
  font-weight: bold;
  font-size: 3em;
  text-align: left;
}
.button{
  text-align: center;
  width: 100%;
  position: absolute;
  display: block;
}
.enter{
  text-align: center;
  display: flex;
  align-items: center;
  justify-content: center;
  top: 50%;
  left: 40%;

}
#out {
  position: absolute;
  width: 100vw;
}
.in {
  margin: 0.1vh auto;
  position: absolute;
  left: 50vw;
  transform: translate(-50%,-50%);
}
#title {
  top: 25vh;
  font-size: 6vh;
  font-weight: bolder;
  width: 100%;
  text-align: center;
}
#context {
  top: 36vh;
  font-size: 4vh;
  font-weight: bold;
  width: 100%;
  text-align: center;
}
</style>
