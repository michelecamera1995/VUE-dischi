<template>
  <div id="main">
    <div class="top-bar">
      <img
        class="spotify-logo"
        src="@/assets/spotify-logo.png"
        alt="spotify logo"
      />
    </div>
    <div id="ciao" v-if="musics.length > 0">
      <musicCard v-for="(music, index) in musics" :key="index" :music="music" />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import musicCard from "@/components/musicCard.vue";

export default {
  name: "mainComponent",
  data() {
    return {
      musics: [],
      url: "https://flynn.boolean.careers/exercises/api/array/music",
    };
  },
  mounted() {
    this.getMusic();
  },
  methods: {
    getMusic() {
      axios.get(this.url).then((response) => {
        console.log(response.data.response);
        this.musics = response.data.response;
        console.log(this.musics);
      });
    },
  },
  components: {
    musicCard,
  },
};
</script>

<style lang="scss" scoped>
#main {
  background-color: grey;
  width: 100vw;
  height: 100vh;
}
#ciao {
  padding: 2%;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  width: 100%;
}
.top-bar {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  background-color: darkslategray;
  height: 10%;
  .spotify-logo {
    margin-left: 50px;
    width: 50px;
    height: 50px;
  }
}
</style>
