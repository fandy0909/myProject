<script setup lang="ts"></script>

<template>
  <div class="grid-page">grid 布局</div>
  <div class="layout">
    <div class="box">box方块</div>
    <div class="box">box方块</div>
    <div class="box">box方块</div>
    <div class="box">box方块</div>
    <div class="box">box方块</div>
    <div class="box">box方块</div>
    <div class="box">box方块</div>
    <div class="box">box方块</div>
    <div class="box">box方块</div>
    <div class="box">box方块</div>
  </div>
</template>

<style lang="scss" scoped>
.grid-page {
  text-align: center;
  padding: 20px 0;
  font-size: 36px;
  font-weight: bold;
}

.layout {
  width: 1400px;
  min-height: 500px;
  background: #fff;
  border-radius: 10px;
  margin: 0 auto;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.5);
  padding: 30px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}

.layout .box {
  width: 300px;
  height: 200px;
  background: #7c9fb0;
  border-radius: 8px;
  padding: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #fff;
  margin-bottom: 40px;
}
</style>
