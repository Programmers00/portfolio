<template>
  <BaseBox :bgColorData="bgColorData">
    <!-- title -->
    <template v-slot:title> Career </template>
    <!-- content -->
    <template v-slot:content>
      <div class="careerContent">
        <CareerCard
          v-for="{
            companyLogoSrc,
            companyName,
            careerPeriod,
            careerDetail,
            projectData,
          } in careerData"
          v-bind:key="companyName"
        >
          <template v-slot:companyLogo
            ><img
              :src="`/assets/images/${companyLogoSrc}.png`"
              alt="Logo"
              width="100%"
          /></template>
          <template v-slot:companyName>{{ companyName }} </template>
          <template v-slot:careerPeriod>
            {{ careerPeriod }}
          </template>
          <template v-slot:careerDetail>
            <div v-for="careerData in careerDetail" v-bind:key="careerData">
              {{ careerData }}
            </div>
          </template>
          <template v-slot:careerProject>
            <div
              class="careerProjectBox"
              v-for="{
                projectTitle,
                projectSubtitle,
                projectPeriod,
                projectCareer,
              } in projectData"
              v-bind:key="projectTitle"
            >
              <div class="projectTitleBox">
                <div class="projectTitle">{{ projectTitle }}</div>
                <div class="projectSubtitle">{{ projectSubtitle }}</div>
                <div class="projectPeriod">{{ projectPeriod }}</div>
              </div>
              <div
                class="projectCareer"
                v-for="projectCareerData in projectCareer"
                v-bind:key="projectCareerData"
              >
                {{ projectCareerData }}
              </div>
            </div>
          </template>
        </CareerCard>
      </div>
    </template>
  </BaseBox>
</template>

<script>
import BaseBox from "@/components/BaseBox.vue";
import CareerCard from "@/components/CareerCard.vue";
export default {
  name: "Career",
  components: {
    BaseBox,
    CareerCard,
  },
  data: () => ({
    bgColorData: "black",
    careerData: [
      {
        companyLogoSrc: "thubCompany",
        companyName: "Thub Company, Corp",
        careerPeriod: "Sep 2021 - ing",
        careerDetail: [
          "Assists with the creation of websites",
          "Provides website maintenance and enhancements",
          "Writes functional requirement documents and specifications",
          "Creates quality mockups and prototypes on tight timelines",
          "Assists back-end developers with coding and troubleshooting",
          "Creates cascading style sheets (CSS) that are consistent across all",
          "browsers and platforms",
          "Stays up-to-date on emerging technology and innovation",
        ],
        projectData: [
          // project3
          {
            projectTitle: "Inteligious Infecitous Disease Control System",
            projectSubtitle:
              "in Busan Portauthority(Ministry of the interiorand safety)",
            projectPeriod: "Jun 2022 - ing",
            projectCareer: [
              "Create Re-usable Components",
              "Main Managing System Logic",
              "Dashboard Page",
              "Handling Mock-up and Api data",
              "MQTT, API connection",
              "Scheduler operation",
            ],
          },
          // project2
          {
            projectTitle: "Warehouse Managing System 1.0 / 2.0",
            projectSubtitle: "in Ulju County Office",
            projectPeriod:
              "Mar 2022 - May 2022 (2.0) / Jun 2021 - Oct 2021 (1.0)",
            projectCareer: [
              "Main Warehousing Managing System Logic",
              "Responsive web site",
              "CRUD Query for managing system page",
              "Refactoring the code",
              "Re-usable Components creation",
              "Improving performance with resolving memory leaking",
            ],
          },
          // project1
          {
            projectTitle: "THUB Company Solution Framework 1.0 / 2.0",
            projectSubtitle: "in Thub Comapny",
            projectPeriod:
              "Jan 2022 - Feb 2022 (2.0) / Sep 2021 - Nov 2021 (1.0)",
            projectCareer: [
              "Handling Mock-up and Api Data",
              "Responsive web site",
              "Refactoring the code",
              "DevExtreme tools",
              "Echart Tools",
            ],
          },
        ],
      },
    ],
  }),
};
</script>

<style lang="scss">
.careerContent {
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  justify-self: center;
  flex-wrap: wrap;
  padding-block: 25px;
  color: white;
  height: auto;
  gap: 30px;
  .projectTitle {
    font-weight: 500;
    font-size: 30px;
    line-height: 34px;
  }
  .projectSubtitle {
    font-weight: 400;
    font-size: 15px;
    line-height: 19px;
  }
  .projectPeriod {
    font-weight: 300;
    font-size: 20px;
    line-height: 24px;
    padding-block: 15px;
  }
  .projectCareer {
    padding-block: 5px;
    font-weight: 200;
    font-size: 20px;
    line-height: 24px;
  }
}
</style>
