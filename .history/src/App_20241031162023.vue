<template>
  <h1>Bonjour</h1>
  <p>Ca va ??</p>
  <button @click="changeMessage">Changer le message</button>
  <p>{{ message }}</p>

  <button @click="toggleColor">Toggle color</button>
  <p :style="{ color: color }">{{ message }}</p>
  <button @click="handleClick">Clic</button>
  <input
    @keydown.enter="handleKeydown"
    type="text"
    placeholder="Tapez Enter pour afficher une alerte"
  />
  <p>{{ count }}</p>
  <button @click="handleClickCount">Count up</button>
  <button @click="handleClickCountDecrease">Count down</button>
</template>

<script setup>
const message = "Bonjour";

import { ref } from "vue";

const color = ref("red");
const toggleColor = () => {
  color.value = color.value === "red" ? "blue" : "red";
};

const handleClick = () => {
  alert("Vous avez cliqué sur le bouton");
};

const handleKeydown = () => {
  alert("Vous avez appuyé sur la touche Enter");
};

const count = ref(0);
</script>

<style>
p {
  color: red;
}
</style>
