<template>
  <BaseBox :bgColorData="bgColorData">
    <!-- title -->
    <template v-slot:title> Projects </template>
    <!-- content -->
    <template v-slot:content>
      <div class="projectsContent">
        <ProjectCard
          v-for="{
            projectTitle,
            projectDuration,
            projectImgSrc,
            projectSubtitle,
            projectSummary,
            projectDetailData,
          } in projectData"
          v-bind:key="projectTitle"
        >
          <template v-slot:projectTitle>{{ projectTitle }} </template>
          <template v-slot:projectDuration>{{ projectDuration }} </template>
          <template v-slot:projectImg>
            <img
              width="100%"
              :src="`/assets/images/${projectImgSrc}.png`"
              alt="No Image"
            />
          </template>
          <template v-slot:projectSubtitle>{{ projectSubtitle }} </template>
          <template v-slot:projectSummary>{{ projectSummary }} </template>
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
    bgColorData: "white",
    projectData: [
      {
        projectTitle: "NOhBUG Portfolio Website",
        projectDuration: "(Sep 2022 personal project)",
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
        projectDuration: "(July 2022 - ing personal project)",
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
  padding-block: 25px;
  color: white;
  height: auto;
  gap: 30px;
}

.key {
  min-width: 230px;
  font-weight: 700;
  font-size: 30px;
  line-height: 30px;
}
.value {
  max-width: 510px;
  word-break: break-all;
  font-weight: 400;
  font-size: 28px;
  line-height: 28px;
}
</style>
