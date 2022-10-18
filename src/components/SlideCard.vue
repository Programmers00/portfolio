<template>
  <div class="mainSlideCard">
    <!-- slide Img Content -->
    <div class="slideWrapper">
      <img
        class="img"
        v-for="item in projectImgSrc"
        v-bind:key="item"
        width="100%"
        :src="`/assets/images/projects/${item}.png`"
        alt="No Image"
      />
    </div>
    <!-- button Box -->
    <div class="btnBox">
      <!-- prev Button -->
      <p @click="clickBtn('prev')" class="prevText">Prev</p>
      <button class="prevBtn" @click="clickBtn('prev')">
        <img
          class="prevImg"
          :src="`/assets/images/${leftBtnImg}.png`"
          alt="Prev"
          width="30%"
        />
      </button>
      <!-- next Button -->
      <p @click="clickBtn('next')" class="nextText">Next</p>
      <button class="nextBtn" @click="clickBtn('next')">
        <img
          class="nextImg"
          :src="`/assets/images/${rightBtnImg}.png`"
          alt="Next"
          width="30%"
        />
      </button>
    </div>
  </div>
</template>

<script>
const imgWidth = 340;
export default {
  name: "SlideCard",
  components: {},
  data: () => ({
    leftBtnImg: "stop",
    rightBtnImg: "arrowRight",
    currentImgNumber: 0,
    imgWrapperWidth: 0,
    imgWidth: "340px",
    tempMarginLeft: 0,
    marginLeft: 0,
  }),
  props: {
    projectImgSrc: {
      type: Array,
      default: [],
    },
  },
  mounted() {
    // init slide
    this.initSlide();
  },
  methods: {
    /** init slide setting */
    initSlide() {
      const totalImgCount = this.projectImgSrc.length;
      this.imgWidth = imgWidth + "px";
      this.imgWrapperWidth = totalImgCount * imgWidth + "px";
      // when total image count is less than 1 or 1, right button is "stop"
      if (totalImgCount <= 1) this.rightBtnImg = "stop";
    },
    /** click button function */
    clickBtn(event) {
      // total image count
      const totalImgCount = this.projectImgSrc.length;
      // click prev button and current image number is not 0
      if (event === "prev" && this.currentImgNumber !== 0) {
        this.tempMarginLeft += imgWidth;
        this.currentImgNumber -= 1;
      }
      // click next button and current image number is less than total image count -1
      else if (event === "next" && this.currentImgNumber < totalImgCount - 1) {
        this.tempMarginLeft -= imgWidth;
        this.currentImgNumber += 1;
      }
      this.marginLeft = this.tempMarginLeft + "px"; //left margin
      this.changeBtnIcon(totalImgCount); //change button icon
    },
    /** change button icon depending on currentImgNumber */
    changeBtnIcon(totalImgCount) {
      this.currentImgNumber === 0
        ? (this.leftBtnImg = "stop")
        : (this.leftBtnImg = "arrowLeft");
      this.currentImgNumber >= totalImgCount - 1
        ? (this.rightBtnImg = "stop")
        : (this.rightBtnImg = "arrowRight");
    },
  },
};
</script>

<style lang="scss" scopedSlots>
.mainSlideCard {
  margin: 0 auto;
  overflow: hidden;
  max-width: v-bind(imgWidth);
  .slideWrapper {
    width: v-bind(imgWrapperWidth);
    margin-left: v-bind(marginLeft);
    .img {
      width: v-bind(imgWidth);
      float: left;
      mix-blend-mode: luminosity;
    }
  }
  .btnBox {
    position: relative;
    width: v-bind(imgWidth);
    display: flex;
    margin: 0 auto;
    .prevText,
    .nextText {
      position: absolute;
      align-content: center;
      font-size: 1.3rem;
      font-weight: 700;
      margin: 1.3rem;
      text-align: center;
    }
    .prevText {
      left: 3rem;
    }
    .nextText {
      right: 3rem;
    }
    .prevBtn,
    .nextBtn {
      display: flex;
      justify-content: center;
      align-items: center;
      border-style: none;
      color: black;
      width: 50%;
      height: 10%;
      transition: transform 0.5s;
      opacity: 0;
      transform: scale(0.9);
    }
    .prevBtn:hover {
      opacity: 1;
      transform: translateX(-55px) scale(0.8);
    }
    .nextBtn:hover {
      opacity: 1;
      transform: translateX(55px) scale(0.8);
    }
  }
}
</style>
