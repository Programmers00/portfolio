<template>
  <div class="mainProjectCard">
    <div class="projectTitleBox">
      <!-- projectTitle -->
      <div class="projectTitle">
        <slot name="projectTitle">Project Title </slot>
      </div>
      <!-- projectPeriod -->
      <div class="projectPeriod">
        <slot name="projectPeriod">Project Info</slot>
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
          <slot name="projectSubtitle">Project Subtitle</slot>
        </div>
        <!-- projectSummary -->
        <div class="projectSummary">
          <slot name="projectSummary">Project Summary</slot>
        </div>
        <hr width="100%" />
        <!-- projectDetail -->
        <div class="projectDetail">
          <slot name="projectDetail">
            <div>Project Detail</div>
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
  padding-block: 1.5rem;
  padding-inline: 3rem;
  background-color: white;
  display: flex;
  color: black;
  height: auto;
  flex-direction: column;
  flex-wrap: wrap;
  width: 95%;
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
      font-size: 2rem;
      line-height: 2rem;
      @include lg {
        font-size: 3.5rem;
        line-height: 3.5rem;
      }
    }
    .projectPeriod {
      text-align: center;
      font-weight: 400;
      font-size: 1.2rem;
      line-height: 1.2rem;
      @include lg {
        font-size: 2rem;
        line-height: 2rem;
      }
    }
  }
  .projectContent {
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    justify-content: space-evenly;
    justify-self: center;
    padding-block: 4rem;
    gap: 2rem;
    @include lg {
      flex-direction: row;
      max-width: 100%;
    }
    .projectImg {
      flex: 1;
    }
    .projectInfoBox {
      display: flex;
      @include lg {
        flex: 2;
      }
      flex-wrap: wrap;
      flex-direction: column;
      gap: 2.5rem;
      .projectSubtitle {
        font-weight: 700;
        font-size: 1.5rem;
        line-height: 1.5rem;
        @include lg {
          font-size: 2.5rem;
          line-height: 2.5rem;
        }
      }
      .projectSummary {
        font-weight: 400;
        font-size: 1.5rem;
        line-height: 1.5rem;
        @include lg {
          font-size: 2.5rem;
          line-height: 2.5rem;
        }
      }
      .projectDetail {
        // gap: 20px;
        gap: 1rem;
        display: flex;
        flex-wrap: wrap;
        flex-direction: column;
      }
    }
  }
}
</style>
