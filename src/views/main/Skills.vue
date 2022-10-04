<template>
  <BaseBox :bgColorData="bgColorData">
    <!-- title -->
    <template v-slot:title><a :name="`${title}`" />{{ title }}</template>
    <!-- content -->
    <template v-slot:content>
      <div class="skillsContent">
        <!-- image card -->
        <ImgCard v-for="imgItem in imgData" v-bind:key="imgItem">
          <!-- title -->
          <template v-slot:imgTitle> {{ imgItem.toUpperCase() }} </template>
          <!-- image -->
          <template v-slot:imgSrc
            ><img :src="`/assets/images/${imgItem}.png`" height="60rem"
          /></template>
        </ImgCard>
      </div>
    </template>
  </BaseBox>
</template>

<script>
import BaseBox from "@/components/BaseBox.vue";
import ImgCard from "@/components/ImgCard.vue";
export default {
  name: "Skills",
  components: {
    BaseBox,
    ImgCard,
  },
  data: () => ({
    /** style data */
    bgColorData: "white",
    /** data */
    title: "Skills",
    imgData: [
      "vue",
      "html",
      "css",
      "js",
      "figma",
      "git",
      "github",
      "gitlab",
      "sourceTree",
      "flutter",
      "sts",
      "postgre",
      "dbeaver",
    ],
  }),
};
</script>

<style lang="scss">
.skillsContent {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  padding-block: 1.5rem;
  color: white;
  height: auto;
}
</style>
