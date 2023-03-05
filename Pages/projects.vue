<template>
  <h2>PROJECTS</h2>
  <div v-if="data" v-for="project in data" class="container">
    <h1>{{ project.title }}</h1>
    <p>{{ project.description }}</p>
    <!-- <p v-if="project.deployedLink">{{ project.deployedLink }}</p> -->
    <div class="linkContainer">
      <a :href="project.deployedLink" target="_blank">deployed site</a>
      <a :href="project.githubLink" target="_blank">github</a>
    </div>
    <img v-if="project.imageUrl" :src="project.imageUrl" />
  </div>
</template>

<script setup>
const query = groq`*[_type == "project"]{
    title,
    date,
    place,
    description,
    "imageUrl": image.asset->url,
    deployedLink,
    githubLink
}`;
const { data } = useSanityQuery(query);
if (data) console.log(data);
</script>

<style scoped lang="scss">
.container {
  width: 60em;
  display: flex;
  flex-direction: column;
  align-items: center;
  p {
    height: 100%;
    width: 100%;
  }
}
img {
  height: 27em;
  width: 50em;
}
.linkContainer {
  display: flex;
  flex-direction: row;
  justify-content: center;
  a {
    padding: 0.5em;
  }
}
</style>
