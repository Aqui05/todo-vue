<template>
  <p>{{ count }}</p>
  <button v-on:click="increment">incrémenté</button>
  <button v-on:click="decrement">décrémenté</button>
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
