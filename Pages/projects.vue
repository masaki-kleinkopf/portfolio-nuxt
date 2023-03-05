<template>
  <div>PROJECTS</div>
  <div>
    <h1>{{ data[0].title }}</h1>
    <p>{{ data[0].description }}</p>
    <img :src="data[0].imageUrl" />
  </div>
</template>

<script setup>
const query = groq`*[_type == "project"]{
    title,
    date,
    place,
    description,
    "imageUrl": image.asset->url
}`;
const { data } = useSanityQuery(query);
</script>

<style scoped lang="scss">
img {
  height: 27em;
  width: 50em;
}
</style>
