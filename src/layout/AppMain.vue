<template>
  <main>
    <Who />
    <Skills />
    <Archiving />
  </main>
</template>

<script>
import Who from "@/views/main/Who.vue";
import Skills from "@/views/main/Skills.vue";
import Archiving from "@/views/main/Archiving.vue";
export default {
  name: "AppMain",
  components: {
    Who,
    Skills,
    Archiving,
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
