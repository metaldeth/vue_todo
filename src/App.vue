<script setup lang="ts">
  import { ref } from 'vue'

  const count = ref(0)

  function increment() {
    count.value++
  }

  function decrement() {
    count.value--
  }
</script>

<template>
  <div>
    <h1>Vue Todo</h1>
    <p>{{ count }}</p>
    <button @click="increment">+</button>
    <button @click="decrement">-</button>
  </div>
</template>

<style scoped>
h1 {
  font-size: 1.5rem;
}
</style>
