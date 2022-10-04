<template>
  <footer class="mainFooterBox">
    <ul class="footerIconsBox">
      <!-- footer icon: repeat-->
      <div v-for="{ url, imgSrc } in iconsData" v-bind:key="url">
        <a :href="url" target="_blank">
          <img
            :src="`/assets/images/${imgSrc}.png`"
            :alt="`${imgSrc}`"
            height="50rem"
        /></a>
      </div>
    </ul>
    <!-- copyright -->
    <a class="footerCopyright" href="#"
      >Copyright © NOhBUG all rights reserved.</a
    >
  </footer>
</template>

<script>
export default {
  name: "AppFooter",
  components: {},
  data: () => ({
    /** data */
    iconsData: [
      {
        url: "https://www.linkedin.com/in/eunshin-noh-b58a06223/",
        imgSrc: "linkedin",
      },
      {
        url: "https://github.com/Programmers00/",
        imgSrc: "github",
      },
      {
        url: "https://programmers.tistory.com/",
        imgSrc: "tistory",
      },
      {
        url: "https://www.instagram.com/eunshinnoh/",
        imgSrc: "instagram",
      },
      {
        url: "https://www.facebook.com/eunshin.noh",
        imgSrc: "facebook",
      },
      {
        url: "https://mail.google.com/mail/?view=cm&fs=1&tf=1&to=nes0410@gmail.com",
        imgSrc: "gmail",
      },
    ],
  }),
};
</script>

<style lang="scss">
.mainFooterBox {
  width: 100%;
  height: 250px;
  background-color: $white;
  flex-direction: column;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
  gap: 30px;
  .footerIconsBox {
    align-items: center;
    justify-content: center;
    display: flex;
    flex-wrap: wrap;
    gap: 15px;
  }
  .footerCopyright {
    font-weight: 400;
    // font-size: 20px;
    // line-height: 24px;
    font-size: 1rem;
    line-height: 1rem;
    @include lg {
      font-size: 1.3rem;
      line-height: 1.3rem;
    }
  }
}
</style>
