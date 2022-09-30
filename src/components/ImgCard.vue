<template>
  <div class="mainImgCard">
    <!-- imgTitle -->
    <div class="imgTitle">
      <slot name="imgTitle"><p>Default title</p> </slot>
    </div>
    <!-- imgContent -->
    <div class="imgSrc">
      <slot name="imgSrc"> Logo </slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "ImgCard",
  components: {},
};
</script>

<style lang="scss">
.mainImgCard {
  display: flex;
  color: black;
  height: auto;
  flex-direction: column;
  flex-wrap: wrap;
  padding: 20px;
  justify-content: center;
  align-items: center;
  gap: 20px;
  .imgTitle {
    font-weight: 700;
    font-size: 32px;
  }
  .imgSrc {
    mix-blend-mode: luminosity;
  }
}
</style>
