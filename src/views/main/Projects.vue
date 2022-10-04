<template>
  <BaseBox :bgColorData="bgColorData">
    <!-- title -->
    <template v-slot:title><a :name="`${title}`" />{{ title }}</template>
    <!-- content -->
    <template v-slot:content>
      <div class="projectsContent">
        <!-- projects repeat -->
        <ProjectCard
          v-for="{
            projectTitle,
            projectPeriod,
            projectImgSrc,
            projectSubtitle,
            projectSummary,
            projectDetailData,
          } in projectData"
          v-bind:key="projectTitle"
        >
          <!-- project title -->
          <template v-slot:projectTitle>{{ projectTitle }} </template>
          <!-- project period -->
          <template v-slot:projectPeriod>{{ projectPeriod }} </template>
          <!-- project image -->
          <template v-slot:projectImg>
            <img
              width="100%"
              :src="`/assets/images/${projectImgSrc}.png`"
              alt="No Image"
            />
          </template>
          <!-- project subtitle -->
          <template v-slot:projectSubtitle>{{ projectSubtitle }} </template>
          <!-- project summary -->
          <template v-slot:projectSummary>{{ projectSummary }} </template>
          <!-- project detail repeat-->
          <template v-slot:projectDetail>
            <div
              style="display: flex; flex-direction: row; flex-wrap: wrap"
              v-for="(value, key) in projectDetailData"
              v-bind:key="key"
            >
              <div class="key">{{ key.toUpperCase() }}</div>
              <div class="value">{{ value }}</div>
            </div>
          </template>
        </ProjectCard>
      </div>
    </template>
  </BaseBox>
</template>

<script>
import BaseBox from "@/components/BaseBox.vue";
import ProjectCard from "@/components/ProjectCard.vue";
export default {
  name: "Projects",
  components: {
    BaseBox,
    ProjectCard,
  },
  data: () => ({
    /** style data */
    bgColorData: "white",
    /** data */
    title: "Projects",
    projectData: [
      {
        projectTitle: "NOhBUG Portfolio Website",
        projectPeriod: "(Sep 2022 personal project)",
        projectImgSrc: "portfolio",
        projectSubtitle: "This is my portfolio website which you are seeing",
        projectSummary:
          "It shows my information, Skills, Archivings, Projects and Career.",
        projectDetailData: {
          feature: "Information summary, Skills, Archivings, Projects, Career",
          git: "https://github.com/Programmers00/portfolio",
          url: "Getting Ready",
          frontEnd: "Vue, javascript, sass, html, sass",
          deployment: "netlify",
        },
      },
      {
        projectTitle: "Baby Sleep",
        projectPeriod: "(July 2022 - ing personal project)",
        projectImgSrc: "babySleep",
        projectSubtitle:
          "This application is white noise application for my baby",
        projectSummary:
          "I made it for learning flutter and putting my baby to sleep. The application is getting ready.",
        projectDetailData: {
          feature: "Various white noise, volum control, UI/UX",
          git: "https://github.com/Programmers00/white_noise",
          url: "Getting Ready",
          frontEnd: "Flutter, Dart",
          deployment: "Getting Ready",
        },
      },
    ],
  }),
};
</script>

<style lang="scss">
.projectsContent {
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  justify-self: center;
  flex-wrap: wrap;
  padding-block: 1.5rem;
  color: white;
  height: auto;
  gap: 2rem;
}
.key {
  min-width: 100%;
  font-weight: 700;
  font-size: 1.4rem;
  line-height: 1.4rem;
  @include lg {
    min-width: 16rem;
    font-size: 2.3rem;
    line-height: 2.3rem;
  }
}
.value {
  word-break: break-all;
  font-weight: 400;
  font-size: 1.3rem;
  line-height: 1.3rem;
  @include lg {
    max-width: 40rem;
    font-size: 2rem;
    line-height: 2rem;
  }
}
</style>
