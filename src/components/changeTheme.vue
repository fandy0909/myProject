<script setup lang="ts">
const changeTheme = () => {
  console.log(1)
}
</script>

<template>
  <div class="theme-page">
    <button @click="changeTheme" class="w-300px h-300px bg-pink">change Theme</button>
  </div>
</template>

<style lang="scss" scoped></style>
