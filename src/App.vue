<script setup>
import { ref, watch } from 'vue'

const userInfo = ref({
  name: 'zs',
  age: 18
})
const setUserInfo = () => {
  // userInfo.value = { name: 'ls', age: 20 }
  userInfo.value.age++
}
watch(
  () => userInfo.value.age,
  (oldValue, newValue) => {
    console.log('newValue:', newValue, 'oldValue:', oldValue)
  },
  {
    deep: true
    // immediate: true
  }
)
</script>

<template>
  <div>
    <div>原始数据：{{ userInfo }}</div>
    <button @click="setUserInfo()">点击修改数据</button>
    <div>过滤之后的数据：{{ computedList }}</div>
    <button @click="changeCount()">点击添加数据</button>
  </div>
</template>
<style></style>
