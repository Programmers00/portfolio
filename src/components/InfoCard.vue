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
  padding-block: 0.6rem;
  .infoTitle {
    font-weight: 700;
    font-size: 1.5rem;
    line-height: 1.5rem;
    @include lg {
      font-size: 2rem;
      line-height: 2rem;
    }
  }
  .infoContent {
    display: inline;
    font-weight: 300;
    font-size: 1.3rem;
    line-height: 1.3rem;
    @include lg {
      font-size: 1.8rem;
      line-height: 1.8rem;
    }
  }
}
</style>
