<template>
  <div>
    <h1>Todo List</h1>
    <p v-if="todos.length === 0">Aucun Todo</p>

    <form action="" @submit:prevent="addTodo">
      <input type="text" v-model="newTodoText" placeholder="Nouvelle tâche" />
      <button>Ajouter un Todo</button>
    </form>
    <ul>
      <li v-for="todo in todos" :key="todo.id">{{ todo.text }}</li>
    </ul>
  </div>
</template>

<script setup>
import { ref } from "vue";

const todos = ref([]);

const newTodoText = ref("");
const addTodo = () => {
  todos.value.push({ id: Date.now(), text: newTodoText.value });
  newTodoText.value = "";
};
</script>
