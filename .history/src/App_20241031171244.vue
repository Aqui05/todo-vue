<template>
  <p>Person</p>
  <ul>
    <li>{{ person.name }}</li>
    <li>{{ person.age }}</li>
    <li>{{ person.address.street }}</li>
    <li>{{ person.address.city }}</li>
    <li>{{ person.address.state }}</li>
    <li>{{ person.hobbies.join(", ") }}</li>
    <li v-if="person.isMarried">Married</li>
    <li v-else>Not Married</li>
    <li v-for="child in person.children" :key="child.name">
      {{ child.name }} - {{ child.age }} years old
    </li>
  </ul>
  <button @click="updatePerson">Update</button>
</template>

<script setup>
import { ref } from "vue";

const person = ref({
  name: "John Doe",
  age: 30,
  address: {
    street: "123 Main St",
    city: "New York",
    state: "NY",
  },
  hobbies: ["reading", "painting", "swimming"],
  isMarried: false,
  children: [
    {
      name: "Jane Doe",
      age: 5,
    },
    {
      name: "Bob Doe",
      age: 8,
    },
  ],
  updatePerson() {
    person.value.name = "Jane Smith";
    person.value.age = 28;
    person.value.address.street = "456 Elm St";
    person.value.hobbies.push("cooking");
    person.value.isMarried = true;
    person.value.children.push({
      name: "Alice Doe",
      age: 10,
    });
    console.log("Person updated");
  },
});
</script>
