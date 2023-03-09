<template>
  <h2>Music</h2>
  <div v-if="data">
    <h2>
      {{ data[0].title }}
    </h2>
    <p>{{ data[0].description }}</p>
    <iframe
      style="border-radius: 12px"
      :src="data[0].link"
      width="100%"
      height="352"
      frameBorder="0"
      allowfullscreen=""
      allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture"
      loading="lazy"
    ></iframe>
  </div>
</template>

<script setup>
const query = groq`*[_type == "music"]{
    title,
    date,
    description,
    link,
    linkType
}`;
const { data } = useSanityQuery(query);
if (data) console.log(data);
</script>
<style scoped lang="scss"></style>
