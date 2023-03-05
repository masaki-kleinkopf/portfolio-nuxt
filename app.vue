<template>
  <main>
    <h1>Nuxt Portfolio</h1>
    <NuxtLink to="/projects">Projects</NuxtLink>
    <NuxtLink to="/">About</NuxtLink>
    <NuxtPage />
  </main>
</template>

<style lang="scss" scoped>
main {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
