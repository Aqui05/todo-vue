<template>
  <p>{{ count }}</p>
  <button @click="increment">incrémenté</button>
  <button @click="decrement">décrémenté</button>
</template>

<script setup>
import { ref } from "vue";

const count = ref(0);

function increment() {
  count.value++;
}

function decrement() {
  count.value--;
}
</script>
