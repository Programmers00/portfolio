<template>
  <main>
    <Who />
  </main>
</template>

<script>
import Who from "@/views/main/Who.vue";
export default {
  name: "AppMain",
  components: {
    Who,
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
