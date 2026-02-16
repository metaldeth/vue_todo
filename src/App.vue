<script setup lang="ts">
  import { ref } from 'vue';

  const todos = ref([
    { id: 1, text: 'Изучить Vue 3', done: false },
    { id: 1, text: 'Сделать Todo List', done: false },
  ])
</script>

<template>
  <div v-if="todos.length <= 0">
    Задач нет
  </div>
  <ul v-show="todos.length > 0">
    <li v-for="(todo, index) in todos" :key="todo.id">
      {{ todo.id }} {{ index }} {{ todo.text }} {{ todo.done }}
    </li>
  </ul>
</template>

<style scoped>

</style>
