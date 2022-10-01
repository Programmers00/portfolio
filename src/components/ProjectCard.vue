<template>
  <div class="mainProjectCard">
    <div class="projectTitleBox">
      <!-- projectTitle -->
      <div class="projectTitle">
        <slot name="projectTitle"><p>Default projectTitle</p> </slot>
      </div>
      <!-- projectDuration -->
      <div class="projectDuration">
        <slot name="projectDuration">Default projectInfo</slot>
      </div>
    </div>
    <div class="projectContent">
      <!-- projectImg -->
      <div class="projectImg">
        <slot name="projectImg">
          <div>NO IMAGE</div>
          /></slot
        >
      </div>
      <div class="projectInfoBox">
        <!-- projectSubtitle -->
        <div class="projectSubtitle">
          <slot name="projectSubtitle"> project Subtitle</slot>
        </div>
        <!-- projectSummary -->
        <div class="projectSummary">
          <slot name="projectSummary"> project Summary</slot>
        </div>
        <hr width="100%" />
        <!-- projectDetail -->
        <div class="projectDetail">
          <slot name="projectDetail">
            <div>Defalut project Detail</div>
          </slot>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProjectCard",
  components: {},
};
</script>

<style lang="scss">
.mainProjectCard {
  padding-block: 30px;
  padding-inline: 80px;
  background-color: white;
  display: flex;
  color: black;
  height: auto;
  flex-direction: column;
  flex-wrap: wrap;
  width: 100%;
  .projectTitleBox {
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    justify-self: center;
    align-content: center;
    gap: 5px;
    .projectTitle {
      text-align: center;
      font-weight: 700;
      font-size: 45px;
      line-height: 45px;
    }
    .projectDuration {
      text-align: center;
      font-weight: 400;
      font-size: 24px;
      line-height: 24px;
    }
  }
  .projectContent {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: space-evenly;
    justify-self: center;
    padding-block: 50px;
    gap: 30px;
    .projectImg {
      mix-blend-mode: luminosity;
      display: flex;
      flex: 1;
      min-width: 370px;
    }
    .projectInfoBox {
      min-width: 300px;
      display: flex;
      flex: 2;
      flex-wrap: wrap;
      flex-direction: column;
      gap: 50px;
      .projectSubtitle {
        font-weight: 700;
        font-size: 34px;
        line-height: 34px;
      }
      .projectSummary {
        font-weight: 400;
        font-size: 34px;
        line-height: 34px;
      }
      .projectDetail {
        gap: 20px;
        display: flex;
        flex-wrap: wrap;
        flex-direction: column;
      }
    }
  }
}
</style>
