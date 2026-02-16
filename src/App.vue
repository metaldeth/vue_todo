<script setup lang="ts">
  import { ref } from 'vue';

  const todos = ref([
    { id: 1, text: 'Изучить Vue 3', done: false },
    { id: 2, text: 'Сделать Todo List', done: false },
  ])

  function toggleTodo(id: number) {
    const todo = todos.value.find(item => item.id === id);

    if(todo) todo.done = !todo.done;
  }
</script>

<template>
  <div v-if="todos.length <= 0">
    Задач нет
  </div>
  <ul v-show="todos.length > 0">
    <li v-for="(todo, index) in todos" :key="todo.id">
      <button @click="toggleTodo(todo.id)">{{ todo.done }}</button>
      <div>{{ todo.id }} {{ index }} {{ todo.text }} </div>
    </li>
  </ul>
</template>

<style scoped>

</style>
