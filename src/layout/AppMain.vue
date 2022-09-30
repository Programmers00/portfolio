<template>
  <main>
    <Who />
    <Skills />
  </main>
</template>

<script>
import Who from "@/views/main/Who.vue";
import Skills from "@/views/main/Skills.vue";
export default {
  name: "AppMain",
  components: {
    Who,
    Skills,
  },
};
</script>

<style lang="scss">
main {
  width: 100%;
  height: auto;
  padding-top: 100px;
}
</style>
