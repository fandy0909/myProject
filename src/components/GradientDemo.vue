<script setup lang="ts"></script>

<template>
  <div class="page">渐变色背景</div>
</template>

<style lang="scss" scoped>
.page {
  font-size: 32px;
  text-align: center;
  padding: 30px;
  width: 100%;
  min-height: 100vh;
  background: linear-gradient(to bottom, transparent, #fff 400px),
    radial-gradient(90% 300px at left top, #95e0dc, transparent),
    radial-gradient(60% 300px at right top, #d3cbfc, transparent);
}
</style>
