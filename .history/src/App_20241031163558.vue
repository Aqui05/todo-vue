<template>
  <p>{{ count }}</p>
  <button @click="increment">incrémenté</button>
  <button @click="decrement">décrémenté</button>
  <p v-if="count === 0">Le compteur est à zéro.</p>
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
