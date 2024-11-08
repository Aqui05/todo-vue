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

function changeMessage() {
  message = "Hello";
}
function toggleColor() {
  document.body.style.backgroundColor =
    document.body.style.backgroundColor === "white" ? "black" : "white";
}
function handleClick() {
  alert("Clic !");
}
function handleKeydown(event) {
  if (event.key === "Enter") {
    alert("Enter pressé!");
  }
}
</script>

<style>
p {
  color: red;
}
</style>
