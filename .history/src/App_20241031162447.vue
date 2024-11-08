<template>
  <p>{{ count }}</p>
  <button>cliqué</button>
</template>

<script setup>
import { ref } from "vue";

const count = ref(0);

/*setInterval(() => {
  count.value++;
}, 3000);*/

function increment() {
  count.value++;
}

document.querySelector("button").addEventListener("click", increment);
</script>

<style>
p {
  color: red;
}
</style>
