<script setup lang="ts">
// import GridDemo from './components/GridDemo.vue'
// import FlexDemo from './components/FlexDemo.vue'
// import GridDemoPro from './components/GridDemoPro.vue'
// import GridAspectRatio from './components/GridAspectRatio.vue'
// import GridAspectRatioPro from './components/GridAspectRatioSupports.vue'
// import GradientDemo from './components/GradientDemo.vue'
// import TestRef from './components/TestRef.vue'
// import centerCom from './components/center-com.vue'
// import MyInput from './components/MyInput.vue'
// import changeTheme from './components/changeTheme.vue'
// import ComputeDemo from './components/ComputeDemo.vue'
// import watchDemo01 from './components/watchDemo01.vue'
// import watchDemo02 from './components/watchDemo02.vue'
// import watchDemo03 from './components/watchDemo03.vue'
// import watchDemo04 from './components/watchDemo04.vue'
// import watchDemo05 from './components/watchDemo05.vue'
// import watchEffectDemo from './components/watchEffectDemo.vue'
import tsDemo from './components/tsDemo.vue'

import { onMounted, provide, reactive, ref, toRef, toRefs } from 'vue'

// const inp = ref(null)

// onMounted(() => {
//获取模板引用的时机：组件挂载完毕
// console.log(inp.value)
// inp.value.focus()
// })
// const testRef = ref(null)
// const clickFn = () => {
//   inp.value.focus()
// }

// const getCom = () => {
//   console.log(testRef.value.count)
// }
// const count = ref(99)
// // 1、跨级传递普通数据
// provide('theme-color', 'pink')
// // 2、跨级传递响应式数据
// provide('count', count)

// setTimeout(() => {
//   count.value = 999
// }, 2000)

// 3、跨层级传递函数---给子孙后代传递可以修改数据的方法
// provide('changeCount', (newCount: number) => {
//   count.value = newCount
// })

// const txt = ref('123456')
// let car = reactive({ brand: '奔驰', price: 999 })
// const change = () => {
//   // car = reactive({ brand: '特斯拉', price: 888 })  //页面不更新
//   // car = { brand: '特斯拉', price: 888 } //页面不更新
//   car = Object.assign(car, { brand: '特斯拉', price: 888 })
// }

// const { brand, price } = toRefs(car)

// const che = toRef(car, 'brand')
</script>

<template>
  <div>
    <!-- <FlexDemo />
    <GridDemo />
    <GridDemoPro />
    <GridAspectRatio />
    <GridAspectRatioPro /> -->
    <!-- <GradientDemo /> -->
    <!-- <TestRef ref="testRef" />
    <button @click="getCom">获取组件</button> -->

    <!-- <div>
      <input ref="inp" type="text" />
      <button @click="clickFn">点击输入框聚焦</button>
    </div> -->
    <!-- <h1>顶层组件</h1>
    <centerCom /> -->
    <!-- 下面两句代码相等 -->
    <!-- <MyInput v-model="txt"></MyInput> -->
    <!-- 相当于 -->
    <!-- <MyInput :modelValue="txt" @update:modelValue="txt = $event"></MyInput> -->

    <!-- {{ txt }} -->

    <!-- <div  class="btn"></div> -->
    <!-- <GridAspectRatioPro /> -->
    <!-- <changeTheme /> -->
    <!-- <div>{{ car.brand }}</div>
    <div>{{ car.price }}</div>
    <div>{{ brand }}</div>
    <div>{{ price }}</div>
    <div>{{ che }}</div>
    <button @click="change">chenge</button> -->

    <!-- <ComputeDemo /> -->
    <!-- <watchDemo02 /> -->
    <!-- <watchDemo05 /> -->
    <watchEffectDemo />

    <tsDemo />
  </div>
</template>

<style scoped>
.btn {
  width: 300px;
  height: 80px;
  border: 1px solid black;
  /* border-radius: 40px; */
  border-radius: calc(infinity * 1px);
}
</style>
