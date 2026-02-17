<script setup lang="ts">
  import { ref } from 'vue'
  import { EmptyState } from './components/base'
  import { TodoInput, TodoList, type Todo } from './components/todo'

  const newTodoText = ref<string | null>(null)
  const todos = ref<Todo[]>([
    { id: 1, text: 'Изучить Vue 3', done: false },
    { id: 2, text: 'Сделать Todo List', done: false },
  ])

  function toggleTodo(id: number) {
    const todo = todos.value.find((item) => item.id === id)
    if (todo) todo.done = !todo.done
  }

  function addTodo() {
    if (!newTodoText.value?.trim()) return
    todos.value.push({
      id: Date.now(),
      done: false,
      text: newTodoText.value.trim(),
    })
    newTodoText.value = null
  }

  function removeTodo(id: number) {
    todos.value = todos.value.filter((todo) => todo.id !== id)
  }
</script>

<template>
  <EmptyState v-if="todos.length <= 0" message="Задач нет" />
  <TodoInput v-model="newTodoText" @add="addTodo" />
  <TodoList
    :items="todos"
    @toggle="toggleTodo"
    @remove="removeTodo"
  />
</template>

<style scoped>
</style>
