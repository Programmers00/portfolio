<template>
  <BaseBox :bgColorData="bgColorData">
    <!-- title -->
    <template v-slot:title> Who I am </template>
    <!-- content -->
    <template v-slot:content>
      <div class="introContent">
        <p class="intro">
          Front-End Web Developer
          <span style="font-size: 36px"> CHALLENGING </span>
          <span style="font-size: 40px"> POSITIVE </span>
          <span style="font-size: 44px"> FAST-PACED </span>
          <span style="font-size: 40px"> HONEST </span>
          <span style="font-size: 48px"> TENACIOUS </span>
        </p>
      </div>
      <div class="infoContent" v-show="showInfo">
        <InfoCard
          v-for="{ infoTitle, infoContent } in infoData"
          v-bind:key="infoTitle"
        >
          <template v-slot:infoTitle> {{ infoTitle }}</template>
          <template v-slot:infoContent>{{ infoContent }}</template>
        </InfoCard>
      </div>
      <button @click="showInfo = !showInfo">
        {{ showInfo === false ? "SHOW MORE" : "SHOW LESS" }}
      </button>
    </template>
  </BaseBox>
</template>

<script>
import BaseBox from "@/components/BaseBox.vue";
import InfoCard from "@/components/InfoCard.vue";
export default {
  name: "WhoIam",
  components: {
    BaseBox,
    InfoCard,
  },
  data: () => ({
    bgColorData: "black",
    showInfo: false,
    infoData: [
      { infoTitle: "NAME", infoContent: "EUNSHIN NOH" },
      { infoTitle: "DOB", infoContent: "APR 10, 1990" },
      { infoTitle: "MOBILE", infoContent: "825 994 4199" },
      { infoTitle: "EMAIL", infoContent: "nes0410@gmail.com" },
      {
        infoTitle: "ADDRESS",
        infoContent: "310 Cranford Court SE, AB T3M 0W3, Canada",
      },
      {
        infoTitle: "EDUCATION",
        infoContent:
          "Bachelor in Computer Engineering(kumoh national institute of technology, South Korea)",
      },
    ],
  }),
};
</script>

<style lang="scss">
.introContent {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  padding-block: 25px;
  color: white;
  height: auto;
  .intro {
    max-width: 900px;
    font-weight: 700;
    font-size: 60px;
    line-height: 50px;
  }
}
.infoContent {
  width: 100%;
  display: inline-flex;
  flex-direction: row;
  flex-wrap: wrap;
  padding-block: 10px;
  height: auto;
  justify-content: space-between;
  align-items: flex-start;
}
button {
  font-size: 30px !important;
  border: none;
  color: white;
  text-align: center;
  text-decoration: none;
  display: inline-block;
}
</style>
