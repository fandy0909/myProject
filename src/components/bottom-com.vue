<script setup lang="ts">
import { inject } from 'vue'

const themeColor = inject('theme-color')
const count = inject('count')
const changeCount = inject('changeCount')
const clickCount = () => {
  changeCount(9999)
}
</script>

<template>
  <div class="bottom-page" :style="{ background: themeColor }">
    底层组件bottom
    <h2>{{ count }}</h2>
    <button @click="clickCount">更新count</button>
  </div>
</template>

<style lang="scss" scoped></style>
