<template>
  <main>
    <Who />
    <Skills />
    <Archiving />
    <Projects />
    <Career />
  </main>
</template>

<script>
import Who from "@/views/main/Who.vue";
import Skills from "@/views/main/Skills.vue";
import Archiving from "@/views/main/Archiving.vue";
import Projects from "@/views/main/Projects.vue";
import Career from "@/views/main/Career.vue";
export default {
  name: "AppMain",
  components: {
    Who,
    Skills,
    Archiving,
    Projects,
    Career,
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
