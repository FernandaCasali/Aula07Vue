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
    <img alt="Vue logo" class="logo" src="./assets/girls.png" width="300" height="300" />

    <div class="wrapper">
      <HelloWorld msg="Você conseguiu!" />
    </div>
  </header>

  <main>
    <TheWelcome />
    <div class="counter">
      <!-- Texto com cor alternada -->
      <h4 :class="clickCount % 2 === 0 ? 'blue-text' : 'red-text'">
        Contador de cliques: {{ clickCount }}
      </h4>
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
  font-size: 3rem;
  margin-top: 1rem;
  cursor: pointer;
}

/* Cores alternadas para o texto */
.blue-text {
  color: #9623fa;
}

.red-text {
  color: #fa236b;
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
