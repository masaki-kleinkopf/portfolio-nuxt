<template>
  <button @click="$emit('changeDarkMode', !props.darkMode)">
    {{ props.darkMode === true ? "light mode" : "dark mode" }}
  </button>
</template>

<script setup>
const props = defineProps(["darkMode"]);
</script>

<style scoped lang="scss">
button {
  height: 2em;
  border: none;
  border-radius: 0.5em;
}
</style>
