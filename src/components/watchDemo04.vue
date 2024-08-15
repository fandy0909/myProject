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
/** 情况四:监视reactive定义的对象数据类型  */
// watch(person, (newValue, oldValue) => {
//   console.log('person变化了', newValue, oldValue)
// })

// watch(
//   () => {
//     return person.name
//   },
//   (newValue, oldValue) => {
//     console.log('person变化了', newValue, oldValue)
//   }
// )
/** 情况四:监视响应式对象的某个属性,且该属性是基本数据类型,要写成函数的形式  */
// watch(
//   () => person.name,
//   (newValue, oldValue) => {
//     console.log('person变化了', newValue, oldValue)
//   }
// )

// watch(person.car, (newValue, oldValue) => {
//   console.log('person变化了', newValue, oldValue)
// })
// watch(
//   () => person.car,
//   (newValue, oldValue) => {
//     console.log('person变化了', newValue, oldValue)
//   }

/** 情况四:监视响应式对象的某个属性,且该属性是对象数据类型,,可以直接写,也可以写函数,更推荐写成函数的形式  */
watch(
  () => person.car,
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
