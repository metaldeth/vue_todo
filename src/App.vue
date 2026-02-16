<script setup lang="ts">
  import { ref } from 'vue';

  const newTodoText = ref('')

  const todos = ref([
    { id: 1, text: 'Изучить Vue 3', done: false },
    { id: 2, text: 'Сделать Todo List', done: false },
  ])

  /**
   * Переключение статуса задачи
   *
   * @param id Номер задачи
   */
  function toggleTodo(id: number) {
    const todo = todos.value.find(item => item.id === id);

    if(todo) todo.done = !todo.done;
  }

  /**
   * Добавление задачи
   */
  function addTodo() {
    if (!newTodoText.value.trim()) return;

    const newTodo = {
      id: Date.now(),
      done: false,
      text: newTodoText.value.trim()
    }

    todos.value.push(newTodo);
  }
</script>

<template>
  <div v-if="todos.length <= 0">
    Задач нет
  </div>
  <input v-model="newTodoText" />
  <button @click="addTodo()" v-show='newTodoText.length > 0'>Добавить</button>
  <ul v-show="todos.length > 0">
    <li v-for="(todo, index) in todos" :key="todo.id">
      <button @click="toggleTodo(todo.id)">{{ todo.done }}</button>
      <div>{{ todo.id }} {{ index }} {{ todo.text }} </div>
    </li>
  </ul>
</template>

<style scoped>

</style>
