<template>
  <p>{{ count }}</p>
</template>

<script setup>
import { ref } from "vue";

const count = ref(0);

setInterval(() => {
  count.value++;
});
</script>

<style>
p {
  color: red;
}
</style>
