<template>
  <h2>原生版本</h2>
  <div class="frame">
    <h2>这是父组件</h2>
    <h2>年龄为{{ user.agevisble ? user.xage : user.gage }}</h2>
    <el-button type="primary" @click="changeName">修改名字为{{ user.isvisble ? user.gname : user.xname }}</el-button>
    <the-child :the-name="user.isvisble ? user.xname : user.gname"
               :the-agevisble="user.agevisble"
               :the-gage="user.gage"
               :the-xage="user.xage"
                @userAge="toAge"></the-child>
  </div>
</template>

<script setup>
import TheChild from './components/TheChild.vue'
import { reactive } from 'vue'

const user = reactive({ gname: 'Guaning', xname: 'XiaoPeng', isvisble: true, gage: 21, xage: 20, agevisble: true})
// const age = ref(21)
const changeName = () => {
  user.isvisble = !user.isvisble
}
const toAge = () => {
  user.agevisble = !user.agevisble
}
</script>

<style scoped>
body {
  font-family: Inter, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu,
  Cantarell, 'Fira Sans', 'Droid Sans', 'Helvetica Neue', sans-serif;
}

h2 {
  text-align: center;
}

.frame {
  width: 400px;
  margin: 10px auto;
  padding: 20px 20px 50px;
  border: 2px solid #2c3e50;
  border-radius: 10px;
  text-align: center;
}
</style>
