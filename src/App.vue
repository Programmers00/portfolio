<template>
  <div id="app">
    <AppNavbar></AppNavbar>
    <AppMain></AppMain>
    <AppFooter></AppFooter>
  </div>
</template>

<script>
import AppNavbar from "@/layout/AppNavbar.vue";
import AppMain from "@/layout/AppMain.vue";
import AppFooter from "@/layout/AppFooter.vue";

export default {
  name: "App",
  components: {
    AppNavbar,
    AppMain,
    AppFooter,
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
