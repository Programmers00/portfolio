<template>
  <BaseBox :bgColorData="bgColorData">
    <!-- title -->
    <template v-slot:title><a :name="`${title}`" />{{ title }}</template>
    <!-- content -->
    <template v-slot:content>
      <div class="careerContent">
        <!-- career card: repeat -->
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
          <!-- logo image -->
          <template v-slot:companyLogo
            ><img
              :src="`/assets/images/${companyLogoSrc}.png`"
              alt="Logo"
              width="100%"
          /></template>
          <!-- company name -->
          <template v-slot:companyName>{{ companyName }} </template>
          <!-- company career period -->
          <template v-slot:careerPeriod>
            {{ careerPeriod }}
          </template>
          <!-- career detail: repeat -->
          <template v-slot:careerDetail>
            <div v-for="careerData in careerDetail" v-bind:key="careerData">
              {{ careerData }}
            </div>
          </template>
          <!-- career proejct: repeat -->
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
    /** style data */
    bgColorData: "black",
    /** data */
    title: "Career",
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
    font-size: 1.8rem;
    line-height: 1.8rem;
    @include lg {
      font-size: 2.2rem;
      line-height: 2.2rem;
    }
  }
  .projectSubtitle {
    font-weight: 400;
    padding-block: 0.5rem;
    font-size: 0.9rem;
    line-height: 0.9rem;
    @include lg {
      font-size: 1.2rem;
      line-height: 1.2rem;
    }
  }
  .projectPeriod {
    font-weight: 300;
    padding-block: 1rem;
    font-size: 1rem;
    line-height: 1rem;
    @include lg {
      font-size: 1.5rem;
      line-height: 1.5rem;
    }
  }
  .projectCareer {
    padding-block: 5px;
    font-weight: 200;
    font-size: 1.3rem;
    line-height: 1.3rem;
    @include lg {
      font-size: 1.8rem;
      line-height: 2.6rem;
    }
  }
}
</style>
