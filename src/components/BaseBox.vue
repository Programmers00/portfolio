<template>
  <div class="mainBaseBox">
    <div class="titleContent">
      <!-- title -->
      <div class="title">
        <slot name="title"><a>Default title</a> </slot>
      </div>
      <!-- content -->
      <div class="content">
        <slot name="content">Default Content</slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "BaseBox",
  components: {},
  props: {
    bgColorData: {
      type: String,
      default: "black",
    },
  },
  data: () => ({
    // default background color: #212322($black)
    bgColor: "#212321",
    titleColor: "white",
  }),
  mounted() {
    // for css background color binding! black: #212322($black), white: #f7f8f8($white)
    this.bgColor = this.bgColorData === "black" ? "#212321" : "#f7f8f8";
    if (this.bgColorData === "black") {
      this.bgColor = "#212321";
      this.titleColor = "white";
    } else {
      this.bgColor = "#f7f8f8";
      this.titleColor = "black";
    }
  },
};
</script>

<style lang="scss">
.mainBaseBox {
  padding-block: 25px;
  width: 100%;
  height: auto;
  // background color from binding data
  background-color: v-bind(bgColor);
  display: flex;
  align-items: center;
  justify-content: center;
  .titleContent {
    width: 1300px;
    max-width: 1300px;
    background-color: transparent;
    .title {
      width: 100%;
      height: 50px;
      padding-block: 25px;
      font-weight: 700;
      font-size: 34px;
      line-height: 15px;
      color: v-bind(titleColor);
    }
    .content {
      width: 100%;
      height: auto;
    }
  }
}
</style>
