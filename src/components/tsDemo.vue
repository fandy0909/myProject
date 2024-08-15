<script setup lang="ts">
import { type PersonInter, type Persons } from '@/types'
let person: PersonInter = { id: '113', name: 'John', age: 25 }

// let personList: Array<PersonInter> = [
//   { id: '111', name: 'John1', age: 25 },
//   { id: '112', name: 'John2', age: 20 },
//   { id: '113', name: 'John3', age: 28 }
// ]

let personList: Persons = [
  { id: '111', name: 'John1', age: 25 },
  { id: '112', name: 'John2', age: 20 },
  { id: '113', name: 'John3', age: 28 }
]
</script>

<template>
  <div class="ts-page">ts</div>
</template>

<style lang="scss" scoped></style>
