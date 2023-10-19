<script setup>
// import { ref } from 'vue'

// const count = ref(0)
import { reactive } from 'vue'

const state = reactive({ count: 0 })
console.log(state);

const increment = () => {
  state.count++
}

</script>


<template>
  <div class="reactivity">
    <h1>This is an Reactivity page</h1>
    <button @click="increment"> + </button>
    <div>{{ state.count }}</div>
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
