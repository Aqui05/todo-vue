<template>
  <div>
    <h1>Todo List</h1>
    <p v-if="todos.length === 0">Aucun Todo</p>

    <form @submit.prevent="addTodo">
      <input type="text" v-model="newTodoText" placeholder="Nouvelle tâche" />
      <button :disabled="!newTodoText">Ajouter un Todo</button>
    </form>
    <ul>
      <li v-for="todo in todos" :key="todo.id">
        <input type="checkbox" v-model="todo.completed" />
        <span
          :style="{ textDecoration: todo.completed ? 'line-through' : 'none' }"
        >
          {{ todo.text }}
        </span>
        <button @click="removeTodo(todo.id)">Supprimer</button>
      </li>
    </ul>
  </div>
</template>

<script setup>
import { ref } from "vue";

const todos = ref([]);
const newTodoText = ref("");

const addTodo = () => {
  todos.value.push({
    id: Date.now(),
    completed: false,
    text: newTodoText.value,
  });
  newTodoText.value = "";
};

const removeTodo = (id) => {
  todos.value = todos.value.filter((todo) => todo.id !== id);
};
</script>
