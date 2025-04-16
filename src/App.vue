<script setup>
import { ref } from 'vue'

// Contador reativo
const clickCount = ref(0)

// Função que incrementa o contador
const incrementClick = () => {
  clickCount.value++
}
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="Você conseguiu!" />
    </div>
  </header>

  <main>
    <TheWelcome />
    <div class="counter">
      <p>Contador de cliques: {{ clickCount }}</p>
      <button @click="incrementClick">Clique aqui</button>
    </div>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

.counter {
  text-align: center;
  margin-top: 2rem;
}

button {
  padding: 0.5rem 1rem;
  font-size: 1rem;
  margin-top: 1rem;
  cursor: pointer;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
