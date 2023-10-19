<script setup>
import { ref } from 'vue'

const count = ref(0)

console.log(count) // { value: 0 }
console.log(count.value) // 0

count.value++
console.log(count.value) // 1

</script>


<template>
  <div class="reactivity">
    <h1>This is an Reactivity page</h1>
    <button @click="count++">+</button>

    <div>{{ count }}</div>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .reactivity {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
