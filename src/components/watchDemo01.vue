<script setup lang="ts">
import { watch } from 'vue'
import { ref } from 'vue'

let sum = ref(0)
const changeSum = () => {
  sum.value += 1
}

// watch(sum, (newValue, oldValue) => {
//   console.log('sum变化了', newValue, oldValue)
// })
const stopWatch = watch(sum, (newValue, oldValue) => {
  console.log('sum变化了', newValue, oldValue)
  if (newValue >= 10) {
    stopWatch()
  }
})
</script>

<template>
  <div class="watch-page">
    <h1>情况一:监视ref定义的基本数据类型</h1>
    <h1>当前sum:{{ sum }}</h1>
    <n-button @click="changeSum" type="primary"> 点击sum+1 </n-button>
  </div>
</template>

<style lang="scss" scoped></style>
