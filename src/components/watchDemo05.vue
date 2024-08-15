<script setup lang="ts">
import { reactive, watch } from 'vue'

let person = reactive({
  name: 'John',
  age: 18,
  car: {
    c1: '奔驰',
    c2: '宝马'
  }
})

const changeName = () => {
  person.name += '~'
}
const changeAge = () => {
  person.age += 1
}
const changeCar1 = () => {
  person.car.c1 = '本田'
}
const changeCar2 = () => {
  person.car.c2 = '雷克萨斯'
}
const changePerson = () => {
  person.car = { c1: '雅迪', c2: '爱玛' }
}

/** 情况五:监视多个数据  */
// watch(
//   [() => person.name, () => person.car.c1],
//   (newValue, oldValue) => {
//     console.log('person变化了', newValue, oldValue)
//   },
//   { deep: true }
// )

watch(
  [() => person.name, person.car],
  (newValue, oldValue) => {
    console.log('person变化了', newValue, oldValue)
  },
  { deep: true }
)
</script>

<template>
  <div class="watch-page">
    <h1>情况四:监视reactive定义的对象数据类型</h1>
    <h2>姓名:{{ person.name }}</h2>
    <h2>年龄:{{ person.age }}</h2>
    <h2>汽车1:{{ person.car.c1 }}</h2>
    <h2>汽车2:{{ person.car.c2 }}</h2>
    <n-flex>
      <n-button @click="changeName" type="primary"> 修改名字 </n-button>
      <n-button @click="changeAge" type="primary"> 修改年龄 </n-button>
      <n-button @click="changeCar1" type="primary"> 修改车1 </n-button>
      <n-button @click="changeCar2" type="primary"> 修改车2 </n-button>
      <n-button @click="changePerson" type="primary"> 修改整个che </n-button>
    </n-flex>
  </div>
</template>

<style lang="scss" scoped></style>
