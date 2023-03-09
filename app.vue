<template>
  <main>
    <header>
      <h1>Masaki Kleinkopf</h1>
      <div class="nav">
        <NuxtLink :darkMode="darkMode" to="/">About</NuxtLink>
        <NuxtLink to="/projects">Projects</NuxtLink>
        <NuxtLink to="/music">Music</NuxtLink>
      </div>
      <DarkModeSwitch :darkMode="darkMode" @change-dark-mode="changeMode" />
    </header>

    <NuxtPage />
  </main>
</template>

<script setup>
const darkMode = ref(false);
const changeMode = (n) => {
  darkMode.value = n;
  document.getElementsByTagName("html")[0].classList.toggle("dark-mode");
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Mukta:wght@300&family=Tilt+Neon&display=swap");
.dark-mode {
  background-color: black;
}
html {
  color: #4c4e52;
  height: 100vh;
  width: 100vw;
}
main {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  font-family: "Mukta", sans-serif;
  height: 100%;
  width: 100%;
  header {
    h1 {
      margin-left: 5em;
    }
    border-bottom: 1px solid;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    width: inherit;
  }
  .nav {
    width: 10em;
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    a:hover {
      color: black;
    }
    a.nuxt-link-exact-active {
      color: aqua;
    }
  }
}
</style>
