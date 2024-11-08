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
    <li>
      <p>Children:</p>
      <ul>
        <li v-for="child in person.children" :key="child.name">
          {{ child.name }} - {{ child.age }} years old
        </li>
      </ul>
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
});

const updatePerson = () => {
  // Update person data here with random data
  person.value.name = "John Smith";
  person.value.age = Math.floor(Math.random() * 100);
  person.value.address.street = "456 Elm St";
  person.value.address.city = "Los Angeles";
  person.value.address.state = "CA";
  person.value.hobbies = ["cooking", "gardening", "hiking"];
  person.value.isMarried = Math.random() > 0.5;
  person.value.children = [
    {
      name: "Alice Doe",
      age: 3,
    },
    {
      name: "David Doe",
      age: 7,
    },
  ];
};
</script>
