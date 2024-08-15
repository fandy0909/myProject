<script setup lang="ts"></script>

<template>
  <div class="grid-page">grid 高级布局</div>
  <div class="layout">
    <div class="box box1">box方块 占两行两列</div>
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
  padding: 50px 0;
  font-size: 36px;
  font-weight: bold;
}

.layout {
  width: 80%;
  min-height: 600px;
  min-width: 1200px;
  // 双层渐变覆盖
  background: linear-gradient(to bottom, transparent -100px, #fff 200px),
    linear-gradient(to right, #d2eef9, #ffd1de);
  border-radius: 10px;
  margin: 0 auto;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.5);
  padding: 30px;
  /*grid布局 两端对齐，最后一行左对齐*/
  display: grid;
  //   1、自己分配
  //   grid-template-columns: 1fr 2fr 1fr 1fr;
  //   grid-template-columns: 1fr 250px 1fr 1fr;
  //   2、重复(次数，1fr)
  // grid-template-columns: repeat(5, 1fr);
  //   3、自动填充 设置最小最大值（实现响应式布局）
  grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
  gap: 30px;
}

.layout .box {
  background: #645f9f;
  border-radius: 8px;
  padding: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #fff;
}
.layout .box1 {
  // 第一行开始 占两行
  grid-row: 1/3;
  // 第一列开始 占两列
  grid-column: 1/3;
}
</style>
