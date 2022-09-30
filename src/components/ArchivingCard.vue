<template>
  <div class="mainArchivingCard">
    <!-- titleImg -->
    <div class="titleImg">
      <slot name="titleImg"><p>Default title logo</p> </slot>
    </div>
    <!-- url -->
    <div class="url">
      <slot name="url">Default url</slot>
    </div>
    <!-- detail -->
    <div class="detail">
      <slot name="detail">Detail text</slot>
    </div>
    <!-- explore -->
    <div class="explore">
      <a :href="url" target="_blank">EXPLORE INSIGHTS</a>
    </div>
  </div>
</template>

<script>
export default {
  name: "InfoCard",
  components: {},
  props: {
    url: {
      type: String,
      default: "",
    },
  },
  mounted() {
    console.log("##", this.url);
  },
};
</script>

<style lang="scss">
.mainArchivingCard {
  padding: 20px;
  background-color: white;
  display: flex;
  color: black;
  height: auto;
  flex-direction: column;
  flex-wrap: wrap;
  width: 45%;
  min-width: 585px;
  mix-blend-mode: luminosity;
  .titleImg {
    min-width: 250px;
  }
  .url {
    font-weight: 700;
    font-size: 24px;
    line-height: 24px;
  }
  .detail {
    font-weight: 700;
    font-size: 34px;
    line-height: 34px;
    padding-block: 50px;
  }
  .explore {
    font-weight: 700;
    font-size: 34px;
    line-height: 34px;
  }
}
</style>
