<template>
  <div class="ms-card">
    <img class="ms-img" :src="music.poster" alt="music poster" />
    <h3>{{ music.title }}</h3>
    <h4>{{ music.author }}</h4>
  </div>
</template>

<script>
export default {
  name: "musicCard",
  props: {
    music: Object,
  },
};
</script>

<style lang="scss" scoped>
.ms-card {
  border-radius: 10%;
  margin: 1%;
  padding: 1%;
  height: 250px;
  width: calc(100% / 6);
  background-color: darkslategray;
  color: white;
  margin-right: 1%;
  font-size: 1rem;
  .ms-img {
    width: 160px;
  }
}
</style>
