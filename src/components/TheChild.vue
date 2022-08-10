<template>
  <div class="childFrame">
    <h2>这是子组件</h2>
    <h2>名字为{{ theName }}</h2>
    <el-button type="primary" @click="changeAge">修改年龄为{{ theAgevisble ? theGage : theXage }}</el-button>
  </div>
</template>

<script setup>
import { defineProps, defineEmits, reactive} from 'vue'
// const user = reactive({ gname: 'Guaning', xname: 'XiaoPeng', isvisble: true, gage: 21, xage: 20, agevisble: true})

const props = defineProps ({
  theName: {
    type: String,
    required: true
  },
  theAgevisble: {
    type: Boolean,
    required: true
  },
  theGage: {
    type: String,
    required: true
  },
  theXage: {
    type: String,
    required:true
  }
})
const $emit = defineEmits(
  ['userAge']
)
const changeAge = () => {
  $emit('userAge')
}
</script>

<style scoped>
.childFrame {
  margin-top: 10px;
  padding: 20px 20px 50px;
  border: 2px solid #2c3e50;
  border-radius: 10px;
  text-align: center;
}
</style>
