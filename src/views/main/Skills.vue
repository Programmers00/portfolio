<template>
  <BaseBox :bgColorData="bgColorData">
    <!-- title -->
    <template v-slot:title> Skills </template>
    <!-- content -->
    <template v-slot:content>
      <div class="skillsContent">
        <ImgCard v-for="{ imgTitle, imgSrc } in imgData" v-bind:key="imgTitle">
          <template v-slot:imgTitle> {{ imgTitle }} </template>
          <template v-slot:imgSrc
            ><img :src="`/assets/images/${imgSrc}.png`" height="120"
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
  name: "WhoIam",
  components: {
    BaseBox,
    ImgCard,
  },
  data: () => ({
    bgColorData: "white",
    imgData: [
      {
        imgTitle: "VUE",
        imgSrc: "vue",
      },
      {
        imgTitle: "HTML",
        imgSrc: "html",
      },
      {
        imgTitle: "CSS",
        imgSrc: "css",
      },
      {
        imgTitle: "JS",
        imgSrc: "js",
      },
      {
        imgTitle: "GIT",
        imgSrc: "git",
      },
      {
        imgTitle: "GITHUB",
        imgSrc: "github",
      },
      {
        imgTitle: "GITLAB",
        imgSrc: "gitlab",
      },
      {
        imgTitle: "SOURCETREE",
        imgSrc: "sourceTree",
      },
      {
        imgTitle: "FLUTTER",
        imgSrc: "flutter",
      },
      {
        imgTitle: "SPRING TOOL SUITE",
        imgSrc: "sts",
      },
      {
        imgTitle: "POSTGRE",
        imgSrc: "postgre",
      },
      {
        imgTitle: "DBEAVER",
        imgSrc: "dbeaver",
      },
    ],
  }),
};
</script>

<style lang="scss">
.skillsContent {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  padding-block: 25px;
  color: white;
  height: auto;
}
</style>
