<template>
  <BaseBox :bgColorData="bgColorData">
    <!-- title -->
    <template v-slot:title><a :name="`${title}`" />{{ title }}</template>
    <!-- content -->
    <template v-slot:content>
      <div class="archivingContent">
        <!-- archiving repeat -->
        <ArchivingCard
          v-for="{ titleImgSrc, url, detail } in archivingData"
          v-bind:key="titleImgSrc"
          :url="url"
        >
          <!-- image -->
          <template v-slot:titleImg
            ><img :src="`/assets/images/${titleImgSrc}.png`" height="65rem"
          /></template>
          <!-- url -->
          <template v-slot:url>{{ url }}</template>
          <!-- detail -->
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
    /** style data */
    bgColorData: "black",
    title: "Archiving",
    /** data */
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
