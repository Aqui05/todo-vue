<template>
  <p>Person</p>
  <ul>
    <li v-for="(item, index) in person" :key="index">
      {{ item }}
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
