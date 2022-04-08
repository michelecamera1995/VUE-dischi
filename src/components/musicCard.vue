<template>
  <div :v-for="music in musics">
    <img :src="music.poster" alt="music poster" />
    <h3>{{ music.title }}</h3>
    <h4>{{ music.author }}</h4>
  </div>
</template>

<script>
export default {
  props: {
    musics: Array,
  },
};
</script>

<style></style>
