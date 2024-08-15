<script setup lang="ts">
import { reactive, watch } from 'vue'

let person = reactive({
  name: 'John',
  age: 18
})

let obj = reactive({
  a: {
    b: {
      c: 666
    }
  }
})
const changeName = () => {
  person.name += '~'
}

const changeAge = () => {
  person.age += 1
}
/**  reactive定义的对象不可以整体修改
 * 使用Object.assign
 */
const changePerson = () => {
  person = Object.assign(person, { name: 'lose', age: 24 })
}

const test = () => {
  obj.a.b.c = 888
}
/**  情况三:监视reactive定义的对象数据类型 ,且默认开始深度监视*/
watch(person, (newValue, oldValue) => {
  console.log('peoson变化了', newValue, oldValue)
})

watch(obj, (newValue, oldValue) => {
  console.log('obj变化了', newValue, oldValue)
})
</script>

<template>
  <div class="watch-page">
    <h1>情况三:监视reactive定义的对象数据类型</h1>
    <h2>姓名:{{ person.name }}</h2>
    <h2>年龄:{{ person.age }}</h2>
    <h2>test:{{ obj.a.b.c }}</h2>
    <n-flex>
      <n-button @click="changeName" type="primary"> 修改名字 </n-button>
      <n-button @click="changeAge" type="primary"> 修改年龄 </n-button>
      <n-button @click="changePerson" type="primary"> 修改整个人 </n-button>
      <n-button @click="test" type="primary"> test </n-button>
    </n-flex>
  </div>
</template>

<style lang="scss" scoped></style>
