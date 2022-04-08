<template>
  <div id="app">
    <Main />
  </div>
</template>

<script>
import Main from "@/components/mainComponent.vue";
export default {
  name: "App",
  components: {
    Main,
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
* {
  box-sizing: border-box;
  margin: 0px;
  padding: 0px;
}
</style>
