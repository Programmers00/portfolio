<template>
  <div class="mainCareerCard">
    <div class="companyLogoBox">
      <!-- companyLogo -->
      <div class="companyLogo">
        <slot name="companyLogo">Logo</slot>
      </div>
    </div>

    <!-- careerBox -->
    <div class="careerBox">
      <!-- companyName -->
      <div class="companyName">
        <slot name="companyName">Comapny Name</slot>
      </div>
      <!-- careerPeriod -->
      <div class="careerPeriod">
        <slot name="careerPeriod">Career Period</slot>
      </div>
      <!-- careerDetail -->
      <div class="careerDetail">
        <slot name="careerDetail">Career Detail</slot>
      </div>
      <!-- careerProject -->
      <div class="careerProject">
        <slot name="careerProject">Career Project</slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CareerCard",
  components: {},
};
</script>

<style lang="scss">
.mainCareerCard {
  padding-block: 1.5rem;
  padding-inline: 3rem;
  gap: 10px;
  display: flex;
  color: white;
  height: auto;
  flex-direction: column;
  flex-wrap: wrap;
  width: 100%;
  @include lg {
    flex-direction: row;
  }
  .companyLogoBox {
    padding-right: 0;
    width: 100%;
    display: flex;
    flex: 1;
    flex-direction: column;
    flex-wrap: wrap;
    justify-items: center;
    align-content: flex-start;
    border: none;
    @include lg {
      border-right: 1px solid white;
      padding-right: 1.2rem;
    }
    .companyLogo {
      min-width: 250px;
      mix-blend-mode: luminosity;
      background-color: $white;
      padding: 10px;
      border-radius: 35px;
    }
  }
  .careerBox {
    display: flex;
    flex: 1;
    flex-direction: column;
    flex-wrap: wrap;
    justify-content: space-evenly;
    justify-self: center;
    padding-left: 0;
    @include lg {
      padding-left: 1.2rem;
      flex: 3;
    }
    gap: 30px;
    .companyName {
      font-weight: 700;
      font-size: 2.3rem;
      line-height: 2.3rem;
      @include lg {
        font-size: 3.4rem;
        line-height: 3.4rem;
      }
    }
    .careerPeriod {
      font-weight: 400;
      font-size: 1.2rem;
      line-height: 1.2rem;
      @include lg {
        font-size: 1.8rem;
        line-height: 1.8rem;
      }
    }
    .careerDetail {
      display: flex;
      flex-direction: column;
      gap: 1rem;
      font-weight: 200;
      font-size: 1.5rem;
      line-height: 1.5rem;
      @include lg {
        font-size: 2rem;
        line-height: 3rem;
      }
      padding-bottom: 1.2rem;
      border-bottom: 1px solid white;
    }
    .careerProject {
      display: flex;
      flex-direction: column;
      gap: 3rem;
    }
  }
}
</style>
