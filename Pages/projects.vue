<template>
  <div>PROJECTS</div>
  <h1 v-if="data">{{ data[0].title }}</h1>
  <p v-if="data">{{ data[0].description }}</p>
</template>

<script setup>
const query = groq`*[_type == "project"]{
    title,
    date,
    place,
    description
}`;
const { data } = useSanityQuery(query);
</script>

<style scoped></style>
