<template>
  <div id="app">
    <Characters />
  </div>
</template>

<script>
import Characters from "@/components/Characters.vue";

export default {
  name: "App",
  components: {
    Characters,
  },
};
</script>

<style lang="scss">
html,
body {
  box-sizing: border-box;
  width: 100%;
  background: black
    url("https://rickandmortypod.com/wp-content/uploads/2018/11/cropped-RM_page-header_background1-3.png")
    center center no-repeat;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: white;
}
</style>
