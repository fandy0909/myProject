<script setup lang="ts">
const count = 999
const sayHi = () => {
  alert('Hi')
}

/**defineExpose 暴露组件内部的属性和方法供外部使用（通过ref使用，ref可以获取组件实例）*/
defineExpose({
  count,
  sayHi
})
</script>

<template>
  <div class="ref-page">ref{{ count }}</div>
</template>

<style lang="scss" scoped></style>
