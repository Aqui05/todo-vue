<template>
  <div>
    <h1>Todo List</h1>
    <ul>
      <li v-for="todo in todos" :key="todo.id">{{ todo.text }}</li>
    </ul>
  </div>
</template>

<script setup>
import { ref } from "vue";

const todos = ref([]);
</script>
