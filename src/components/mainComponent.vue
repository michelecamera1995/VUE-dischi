<template>
  <div id="main">
    <div class="top-bar">
      <img
        class="spotify-logo"
        src="@/assets/spotify-logo.png"
        alt="spotify logo"
      />
    </div>
    <inputMusic @selectedGenre="getMusicGenre" />
    <div id="ciao" v-if="musics.length > 0">
      <musicCard
        v-for="(music, index) in filteredMusicGenre"
        :key="index"
        :music="music"
      />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import inputMusic from "@/components/inputElement.vue";
import musicCard from "@/components/musicCard.vue";

export default {
  name: "mainComponent",
  // data
  data() {
    return {
      genre: "",
      musics: [],
      url: "https://flynn.boolean.careers/exercises/api/array/music",
    };
  },
  // mounted
  mounted() {
    this.getMusic();
  },
  // methods
  methods: {
    getMusicGenre(genre) {
      this.genre = genre;
      //console.log(genre);
    },
    getMusic() {
      axios.get(this.url).then((response) => {
        this.musics = response.data.response;
      });
    },
  },
  // computed
  computed: {
    filteredMusicGenre() {
      if (this.genre === "") {
        return this.musics;
      } else {
        return this.musics.filter(({ genre }) => genre === this.genre);
      }
    },
  },
  // components
  components: {
    musicCard,
    inputMusic,
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
