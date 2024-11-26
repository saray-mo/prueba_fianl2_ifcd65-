<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <button>boton magico</button>

  <main>
    <TheWelcome />
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

button {
  background-color: rgb(16, 128, 16);
  cursor: pointer;
  border: none;
  padding: 16px 32px;
  color: #fff;
  font-size: 24px;
  font-weight: bold;
  position: relative;
  border-radius: 12px;
}

button::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  z-index: -1;
  width: 100%;
  height: 100%;
  background: linear-gradient(45deg, red, blue, deeppink, blue, red, blue, deeppink);
  background-size: 800%;
  border-radius: 10px;
  filter: blur(8px);
  animation: glowing 20s linear infinite;
}

@keyframes glowing {
  0% {
    background-position: 0, 0;
  }
  50% {
    background-position: 400%, 0;
  }
  100% {
    background-position: 0%, 0;
  }
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
