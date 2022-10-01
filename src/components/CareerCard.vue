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
  padding-block: 30px;
  padding-inline: 80px;
  gap: 10px;
  display: flex;
  color: white;
  height: auto;
  flex-direction: row;
  flex-wrap: wrap;
  width: 100%;
  .companyLogoBox {
    padding-right: 20px;
    width: 100%;
    display: flex;
    flex: 1;
    flex-direction: column;
    flex-wrap: wrap;
    justify-items: center;
    align-content: center;
    border-right: 1px solid white;
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
    flex: 3;
    flex-direction: column;
    flex-wrap: wrap;
    justify-content: space-evenly;
    justify-self: center;
    padding-left: 20px;
    gap: 30px;
    .companyName {
      font-weight: 700;
      font-size: 45px;
      line-height: 45px;
    }
    .careerPeriod {
      font-weight: 400;
      font-size: 24px;
      line-height: 24px;
    }

    .careerDetail {
      font-weight: 200;
      font-size: 24px;
      line-height: 34px;
      padding-bottom: 20px;
      border-bottom: 1px solid white;
    }
    .careerProject {
      display: flex;
      flex-direction: column;
      gap: 50px;
    }
  }
}
</style>
