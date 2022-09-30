<template>
  <div class="mainInfoCard">
    <!-- infoTitle -->
    <div class="infoTitle">
      <slot name="infoTitle"><p>Default title</p> </slot>
    </div>
    <!-- infoContent -->
    <div class="infoContent">
      <slot name="infoContent">Default Content</slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "InfoCard",
  components: {},
};
</script>

<style lang="scss">
.mainInfoCard {
  display: inline-flex;
  color: white;
  width: 100%;
  height: auto;
  flex-direction: column;
  flex-wrap: wrap;
  padding-block: 10px;
  .infoTitle {
    font-weight: 700;
    font-size: 34px;
  }
  .infoContent {
    display: inline;
    font-weight: 300;
    font-size: 30px;
    line-height: 30px;
  }
}
</style>
