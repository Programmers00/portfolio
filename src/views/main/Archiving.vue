<template>
  <BaseBox :bgColorData="bgColorData">
    <!-- title -->
    <template v-slot:title> Archiving </template>
    <!-- content -->
    <template v-slot:content>
      <div class="archivingContent">
        <ArchivingCard
          v-for="{ titleImgSrc, url, detail } in archivingData"
          v-bind:key="titleImgSrc"
          :url="url"
          ><template v-slot:titleImg
            ><img :src="`/assets/images/${titleImgSrc}.png`" height="80"
          /></template>
          <template v-slot:url>{{ url }}</template>
          <template v-slot:detail> {{ detail }} </template>
        </ArchivingCard>
      </div>
    </template>
  </BaseBox>
</template>

<script>
import BaseBox from "@/components/BaseBox.vue";
import ArchivingCard from "@/components/ArchivingCard.vue";
export default {
  name: "Archiving",
  components: {
    BaseBox,
    ArchivingCard,
  },
  data: () => ({
    bgColorData: "black",
    archivingData: [
      {
        titleImgSrc: "githubTitle",
        url: "https://github.com/Programmers00",
        detail: "My source code storage for projects and practice",
      },
      {
        titleImgSrc: "tistoryTitle",
        url: "https://programmers.tistory.com",
        detail: "A record to make what I have studied truly mine",
      },
    ],
  }),
};
</script>

<style lang="scss">
.archivingContent {
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  justify-self: center;
  flex-wrap: wrap;
  padding-block: 25px;
  color: white;
  height: auto;
  gap: 30px;
}
</style>
