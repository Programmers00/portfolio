<template>
  <BaseBox :bgColorData="bgColorData">
    <!-- title -->
    <template v-slot:title
      ><a :name="`${title.replace(/ /g, '')}`" />{{ title }}</template
    >
    <!-- content -->
    <template v-slot:content>
      <div class="introContent">
        <p class="intro">
          Front-End Web Developer
          <span style="font-size: 2.9rem"> CHALLENGING </span>
          <span style="font-size: 3.1rem"> POSITIVE </span>
          <span style="font-size: 3.4rem"> FAST-PACED </span>
          <span style="font-size: 3.1rem"> HONEST </span>
          <span style="font-size: 3.7rem"> TENACIOUS </span>
        </p>
      </div>
      <div class="infoContent">
        <InfoCard
          v-for="{ infoTitle, infoContent } in infoData"
          v-bind:key="infoTitle"
        >
          <template v-slot:infoTitle> {{ infoTitle }}</template>
          <template v-slot:infoContent>{{ infoContent }}</template>
        </InfoCard>
      </div>
      <button @click="showInfoToggle">
        {{ infoBtn === "showMore" ? "SHOW MORE" : "SHOW LESS" }}
      </button>
    </template>
  </BaseBox>
</template>

<script>
import BaseBox from "@/components/BaseBox.vue";
import InfoCard from "@/components/InfoCard.vue";
export default {
  name: "Who",
  components: {
    BaseBox,
    InfoCard,
  },
  data: () => ({
    /** style data */
    infoBtn: "showMore", // "showLess"
    infoContentAnimation: "infoClose",
    /** data */
    title: "Who I am",
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
  methods: {
    showInfoToggle() {
      this.infoBtn = this.infoBtn === "showMore" ? "showLess" : "showMore";
      if (this.infoBtn === "showMore") {
        this.infoContentAnimation = "infoClose";
      } else {
        this.infoContentAnimation = "infoOpen";
      }
    },
  },
};
</script>

<style lang="scss">
@keyframes infoOpen {
  0% {
    opacity: 0;
    visibility: hidden;
    // display: none;
    height: 0;
  }
  25% {
    opacity: 0.25;
    height: 150px;
  }
  50% {
    opacity: 0.5;
    height: 300px;
  }
  75% {
    opacity: 0.75;
    height: 450px;
  }
  100% {
    opacity: 1;
    // display: block;
    height: auto;
  }
}
@keyframes infoClose {
  0% {
    opacity: 1;
    // display: block;
    height: auto;
  }
  25% {
    opacity: 0.75;
    height: 450px;
  }
  50% {
    opacity: 0.5;
    height: 300px;
  }
  75% {
    opacity: 0.75;
    height: 150px;
  }
  100% {
    opacity: 0;
    visibility: hidden;
    // display: none;
    height: 0;
  }
}
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
    // font-size: 60px;
    font-size: 3.9em;
    // line-height: 50px;
    line-height: 3.9rem;
  }
}
.infoContent {
  width: 100%;
  // display: inline-flex;
  // flex-direction: row;
  // flex-wrap: wrap;
  padding-block: 10px;
  // height: auto;
  justify-content: space-between;
  align-items: flex-start;
  animation: v-bind(infoContentAnimation) ease-in 350ms forwards;
}
button {
  // font-size: 30px !important;
  font-size: 2rem !important;
  border: none;
  color: white;
  text-align: center;
  text-decoration: none;
  display: inline-block;
}
</style>
