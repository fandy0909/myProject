button
<script setup lang="ts">
import { computed, ref } from 'vue'

const firstName = ref('fanrong')
const lastName = ref('peng')

// const fullName = computed(() => {
//   return (
//     firstName.value.slice(0, 1).toUpperCase() +
//     firstName.value.slice(1) +
//     '-' +
//     lastName.value.slice(0, 1).toUpperCase() +
//     lastName.value.slice(1)
//   )
// })

const fullName = computed({
  get() {
    return (
      firstName.value.slice(0, 1).toUpperCase() +
      firstName.value.slice(1) +
      '-' +
      lastName.value.slice(0, 1).toUpperCase() +
      lastName.value.slice(1)
    )
  },
  set(val) {
    console.log('set', val.split('-'))
    // const newValue = val.split('-')
    // firstName.value = newValue[0]
    // lastName.value = newValue[1]

    const [str1, str2] = val.split('-')
    firstName.value = str1
    lastName.value = str2
  }
})

const chengeEvent = () => {
  fullName.value = 'li-sa'
}
</script>

<template>
  <div class="p-20px w-300px h-300px bg-blue m-auto text-center">
    名: <input type="text" v-model="firstName" /> <br />
    姓: <input class="mt-3" type="text" v-model="lastName" /> <br />
    <div>{{ firstName }}-{{ lastName }}</div>
    <div>{{ fullName }}</div>
    <button type="button" @click="chengeEvent">修改</button>
  </div>
</template>

<style lang="scss" scoped></style>
