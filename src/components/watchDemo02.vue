<script setup lang="ts">
import { watch } from 'vue'
import { ref } from 'vue'

let person = ref({
  name: 'John',
  age: 18
})
const changeName = () => {
  person.value.name += '~'
}

const changeAge = () => {
  person.value.age += 1
}

const changePerson = () => {
  person.value = { name: 'lose', age: 24 }
}
/**  情况二:监视ref定义的对象数据类型,监视的是对象的地址值
 * 若要想监视对象的内部属性,需要手动开启deep属性
 * watch的第一个参数: 被监视的数据
 * watch的第二个参数: 监视的回调
 * watch的第三个参数: 配置对象(deep,immediate等等...)
 */
watch(
  person,
  (newValue, oldValue) => {
    console.log('person变化了', newValue, oldValue)
  },
  { deep: true }
)
</script>

<template>
  <div class="watch-page">
    <h1>情况二:监视ref定义的对象数据类型</h1>
    <h2>姓名:{{ person.name }}</h2>
    <h2>年龄:{{ person.age }}</h2>
    <n-flex>
      <n-button @click="changeName" type="primary"> 修改名字 </n-button>
      <n-button @click="changeAge" type="primary"> 修改年龄 </n-button>
      <n-button @click="changePerson" type="primary"> 修改整个人 </n-button>
    </n-flex>
  </div>
</template>

<style lang="scss" scoped></style>
