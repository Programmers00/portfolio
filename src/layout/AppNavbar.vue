<template>
  <div class="mainNavbarBox">
    <div class="logoNavBox">
      <div class="logo">NOhBUG</div>
      <div class="nav">
        <ul>
          <li><a href="#whoIam">Who I am</a></li>
          <li><a href="#Skills">Skills</a></li>
          <li><a href="#Archiving">Archiving</a></li>
          <li><a href="#Projects">Projects</a></li>
          <li><a href="#Career">Career</a></li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AppNavbar",
  components: {},
};
</script>
<style lang="scss">
.mainNavbarBox {
  position: fixed;
  width: 100%;
  height: 100px;
  background-color: $black;
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 9999;
  .logoNavBox {
    max-width: 1300px;
    width: 1300px;
    .logo {
      float: left;
      color: white;
      font-weight: 700;
      font-size: 64px;
      line-height: 15px;
    }
    .nav {
      float: right;
      ul {
        font-weight: 700;
        font-size: 22px;
        line-height: 15px;
        list-style-type: none;
        li {
          display: inline;
        }
        a {
          color: white;
          padding: 15px;
        }
      }
    }
  }
}
</style>
