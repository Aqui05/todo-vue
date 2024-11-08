<template>
  <p>{{ count }}</p>
  <button>incrémenté</button>
  <button>décrémenté</button>
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

document.querySelector("button").addEventListener("click", increment);

document
  .querySelector("button:last-child")
  .addEventListener("click", decrement);
</script>
