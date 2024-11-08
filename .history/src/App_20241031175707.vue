<template>
  <button class="button" @click="addTodo">Ajouter un Todo</button>
  <div>
    <h1>Todo List</h1>
    <input v-model="newTodoText" placeholder="Ajouter un Todo" />
    <ul>
      <li v-for="todo in todos" :key="todo.id">{{ todo.text }}</li>
    </ul>
  </div>
</template>

<script setup>
import { ref } from "vue";

const todos = ref([]);

const addTodo = () => {
  const newTodoText = prompt("Nouveau Todo:");
  if (newTodoText) {
    todos.value.push({ id: Date.now(), text: newTodoText });
  }
};
</script>
