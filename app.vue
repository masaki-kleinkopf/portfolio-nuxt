<template>
  <main>
    <h1>Masaki Kleinkopf</h1>
    <div class="nav">
      <NuxtLink to="/">About</NuxtLink>
      <NuxtLink to="/projects">Projects</NuxtLink>
      <NuxtLink to="/music">Music</NuxtLink>
    </div>
    <NuxtPage />
  </main>
</template>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Mukta:wght@300&family=Tilt+Neon&display=swap");
main {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  font-family: "Mukta", sans-serif;
  .nav {
    width: 10em;
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    a:hover {
      color: black;
    }
  }
}
</style>
