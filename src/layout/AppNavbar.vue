<template>
  <!-- main navigation bar Box: scrollDown -> show, scrollUp -> disappear -->
  <div class="mainNavbarBox">
    <!-- menu view: 1200px <= device width -->
    <div class="menuView">
      <!-- navigation menu column -->
      <div class="navMenuCol">
        <ul v-for="href in navData" v-bind:key="href">
          <a :href="`#${href.replace(/ /g, '')}`" @click="toggleMenuView()">{{
            href
          }}</a>
        </ul>
      </div>
    </div>
    <!-- logo and navigation box -->
    <div class="logoNavBox">
      <!-- logo -->
      <a class="logo" href="#">NOhBUG</a>
      <!-- navigation -->
      <div class="nav">
        <!-- menu Iion or X icon:  1200px <= device width -->
        <div class="menuIcon" @click="toggleMenuView">
          <span class="bar"></span>
          <span class="bar"></span>
          <span class="bar"></span>
        </div>
        <!-- navigation menu row -->
        <div class="navMenuRow">
          <ul>
            <li v-for="href in navData" v-bind:key="href">
              <a :href="`#${href.replace(/ /g, '')}`">{{ href }}</a>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AppNavbar",
  components: {},
  data: () => ({
    /** style data */
    // scroll event for navbar hidden or not
    showNavbar: true,
    lastScrollPosition: 0,
    scrollValue: 0,
    mainNavbarTransform: "none", // default "none", scroll evnet => hidden("translate3d(0, -100%, 0)")
    //menuIcon or XIcon
    menuBtn: "menuIcon", // or xIcon
    menuViewToggle: "menuClose",
    // menuViewVisibility: "hidden",
    // menuIcon Style
    menuIconJustifyContent: "space-between", // or "space-evenly"
    secondBtnVisibility: "visible", // or "hidden"
    firstBtnTransform: "none", // or "translateY(9px) rotate(-45deg)"
    lastBtnTransform: "none", // or "translateY(-9px) translateX(0.5px) rotate(45deg)"
    /** data */
    // navigation Data
    navData: ["Who I am", "Skills", "Archiving", "Projects", "Career"],
  }),
  mounted() {
    //scroll event init
    this.initScrollEvent();
  },

  beforeDestroy() {
    // destroy scroll event listener
    window.removeEventListener("scroll", this.onScroll);
  },
  methods: {
    /** initialize scroll event*/
    initScrollEvent() {
      this.lastScrollPosition = window.pageYOffset;
      // add scroll event listener
      window.addEventListener("scroll", this.onScroll);
      const viewportMeta = document.createElement("meta");
      viewportMeta.name = "viewport";
      viewportMeta.content = "width=device-width, initial-scale=1";
      document.head.appendChild(viewportMeta);
    },
    /** scroll event */
    onScroll() {
      const OFFSET = 60;
      if (window.pageYOffset < 0) {
        return;
      }
      if (Math.abs(window.pageYOffset - this.lastScrollPosition) < OFFSET) {
        return;
      }
      this.showNavbar = window.pageYOffset < this.lastScrollPosition;
      this.lastScrollPosition = window.pageYOffset;
      if (this.showNavbar) {
        this.mainNavbarTransform = "none";
      } else {
        this.mainNavbarTransform = "translate3d(0, -100%, 0)";
      }
    },
    /** toggle menu view function : Open or Close  */
    toggleMenuView() {
      this.menuBtn = this.menuBtn === "menuIcon" ? "xIcon" : "menuIcon";
      if (this.menuBtn === "menuIcon") {
        // menuView -> Close
        this.menuViewToggle = "menuClose"; // "opacity:0, visibility: hidden"
        // menuIcon -> xIcon
        this.menuIconJustifyContent = "space-between";
        this.secondBtnVisibility = "visible";
        this.firstBtnTransform = "none";
        this.lastBtnTransform = "none";
      } else {
        // menuView -> Open
        this.menuViewToggle = "menuOpen"; // "opacity:1, visibility: visible"
        // xIcon -> menuIcon
        this.menuIconJustifyContent = "space-evenly";
        this.secondBtnVisibility = "hidden";
        this.firstBtnTransform = "translateY(9px) rotate(-45deg)";
        this.lastBtnTransform =
          "translateY(-9px) translateX(0.5px) rotate(45deg)";
      }
    },
  },
};
</script>
<style lang="scss">
// menu view: Open
@keyframes menuOpen {
  0% {
    opacity: 0;
    visibility: hidden;
  }
  100% {
    opacity: 1;
  }
}
// menu view: Close
@keyframes menuClose {
  0% {
    opacity: 1;
  }
  100% {
    opacity: 0;
    visibility: hidden;
  }
}
.mainNavbarBox {
  position: fixed;
  width: 100%;
  height: 50px;
  @include lg {
    height: 100px;
  }
  background-color: $black;
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 9999;
  transform: v-bind(mainNavbarTransform);
  transition: 250ms transform ease-out;
  .menuView {
    top: 50px;
    position: absolute;
    width: 100%;
    height: 100vh;
    background-color: $black;
    animation: v-bind(menuViewToggle) ease-out 250ms forwards;
    @include lg {
      top: 100px;
      visibility: hidden;
    }
    .navMenuCol {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      gap: 2.5rem;
      padding-block: 2.5rem;
      ul {
        font-weight: 700;
        font-size: 1.7rem;
        line-height: 1.7rem;
        list-style-type: none;
        li {
          display: inline;
        }
        a {
          color: white;
        }
      }
    }
  }
  .logoNavBox {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    max-width: 1300px;
    width: 1300px;
    .logo {
      text-decoration: none;
      color: white;
      font-weight: 700;
      font-size: 2.5rem;
      line-height: 2.5rem;
      @include lg {
        font-size: 4rem;
        line-height: 4rem;
      }
    }
    .nav {
      .menuIcon {
        padding: 5px;
        display: flex;
        align-items: flex-end;
        flex-direction: column;
        height: 40px;
        justify-content: v-bind(menuIconJustifyContent);
        outline: none;
        width: 40px;
        .bar:nth-child(1) {
          height: 4px;
          background-color: white;
          width: 30px;
          transform: v-bind(firstBtnTransform);
          transition: transform 250ms;
        }
        .bar:nth-child(2) {
          height: 4px;
          background-color: white;
          width: 27px;
          @if v-bind(munuIcon) {
            visibility: v-bind(secondBtnVisibility);
          }
        }
        .bar:nth-child(3) {
          height: 4px;
          background-color: white;
          width: 30px;
          transform: v-bind(lastBtnTransform);
          transition: transform 250ms;
        }
        cursor: pointer;
        @include lg {
          display: none;
        }
      }
      .navMenuRow {
        display: none;
        @include lg {
          display: flex;
          ul {
            font-weight: 700;
            font-size: 1.7rem;
            line-height: 1.7rem;
            list-style-type: none;
            li {
              display: inline;
            }
            a {
              color: white;
              padding: 1.2rem;
            }
          }
        }
      }
    }
  }
}
</style>
