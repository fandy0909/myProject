<script setup lang="ts">
import { ref, watch, watchEffect } from 'vue'

const temp = ref(10)
const height = ref(0)

const changeTemp = () => {
  temp.value += 10
}
const changeHeight = () => {
  height.value += 10
}
/**  监视 -- watch实现 */
// watch([temp, height], (value) => {
//   const [tempValue, heightValue] = value
//   if (tempValue >= 50 || heightValue >= 60) {
//     console.log('发送服务器请求')
//   }
// })
/**  监视 -- watchEffect实现 */
watchEffect(() => {
  if (temp.value >= 50 || height.value >= 60) {
    console.log('发送服务器请求')
  }
})
</script>

<template>
  <div class="watchEffect-page">
    <h1>feature01</h1>
    <h1>feature02</h1>
    <h2>需求:</h2>
    <h2>当前水温:{{ temp }}℃</h2>
    <h2>当前水位:{{ height }}CM</h2>
    <n-flex>
      <n-button type="primary" @click="changeTemp">水温+10</n-button>
      <n-button type="primary" @click="changeHeight">水位+10</n-button>
    </n-flex>
  </div>
</template>

<style lang="scss" scoped></style>
