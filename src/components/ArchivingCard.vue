<template>
  <div class="mainArchivingCard">
    <!-- titleImg -->
    <div class="titleImg">
      <slot name="titleImg">Title Logo</slot>
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
    <span>
      <a class="explore" :href="url" target="_blank">EXPLORE INSIGHTS</a>
    </span>
  </div>
</template>

<script>
export default {
  name: "InfoCard",
  // props data from Archiving.vue
  props: {
    url: {
      type: String,
      default: "",
    },
  },
};
</script>

<style lang="scss">
.mainArchivingCard {
  padding: 1rem;
  background-color: white;
  display: flex;
  color: black;
  height: auto;
  flex-direction: column;
  flex-wrap: wrap;
  width: auto;
  @include lg {
    width: 45%;
    min-width: 585px;
  }
  mix-blend-mode: luminosity;
  .titleImg {
    min-width: 200px;
  }
  .url {
    font-weight: 700;
    font-size: 1rem;
    line-height: 1rem;
    @include lg {
      font-size: 1.2rem;
      line-height: 1.2rem;
    }
  }
  .detail {
    font-weight: 700;
    font-size: 1.8rem;
    line-height: 1.8rem;
    padding-block: 2rem;
    @include lg {
      font-size: 2.4rem;
      line-height: 2.4rem;
      padding-block: 3rem;
    }
  }
  // "explore insight" button animation
  .explore {
    font-weight: 700;
    font-size: 1.2rem;
    line-height: 1.2rem;
    @include lg {
      font-size: 1.5rem;
      line-height: 1.5rem;
    }
    border: none;
    color: black;
    text-decoration: none;
    display: inline-block;
  }
  .explore:after {
    border: 1px solid rgba(black, 0);
    content: " ";
    display: block;
    position: relative;
    transition: all 280ms ease-in-out;
    width: 0;
  }
  .explore:hover:after {
    border-color: black;
    transition: width 350ms ease-in-out;
    width: 100%;
  }
}
</style>
