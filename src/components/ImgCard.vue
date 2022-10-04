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
  padding: 1.5rem;
  justify-content: center;
  align-items: center;
  gap: 1rem;
  .imgTitle {
    font-weight: 700;
    font-size: 1.5rem;
    @include lg {
      font-size: 2rem;
    }
  }
  .imgSrc {
    mix-blend-mode: luminosity;
  }
}
</style>
