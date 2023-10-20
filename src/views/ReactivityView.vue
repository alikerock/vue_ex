<script setup>
/*
import { ref } from 'vue'
const count = ref(0)
console.log(count);
const increment = () => {
  count.value++
  console.log(count);
}
*/


/*
  import { reactive } from 'vue'

  const state = reactive({ count: 0 })
  console.log(state);

  const increment = () => {
    state.count++
  }
*/
import { ref, nextTick } from 'vue'

const count = ref(0)

async function increment() {
  count.value++

  // 아직 DOM 업데이트되지 않음.
  console.log(document.getElementById('counter').textContent) // 0

  await nextTick()
  // 이제 DOM 업데이트됨.
  console.log(document.getElementById('counter').textContent) // 1
}

</script>


<template>
  {{console.log('template 실행')}}
  <div class="reactivity">
    <h1>This is an Reactivity page</h1>
    <button @click="increment"> + </button>
    <div id="counter">{{ count }}</div>
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
