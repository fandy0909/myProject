<script setup lang="ts">
import { defineModel } from 'vue'
// defineProps({
//   modelValue: String
// })

// const emit = defineEmits(['update:modelValue'])

const modelValue = defineModel()
</script>

<template>
  <!-- <div class="input-page">
    <input
      type="text"
      :value="modelValue"
      @input="e => emit('update:modelValue', e.target.value)"
    />
  </div> -->

  <div class="input-page">
    <input type="text" :value="modelValue" @input="e => (modelValue = e.target.value)" />
  </div>
</template>

<style lang="scss" scoped></style>
