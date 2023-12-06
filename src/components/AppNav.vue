<script>
export default {
  props: {
    navPosition: String,
    bgColor: String,
    menuBar: Boolean,
    linksArray: Array,
  },
  data() {
    return {
      displayMenu: false,
    };
  },
  methods: {
    showMenu() {
      this.displayMenu = !this.displayMenu;
    },
  },
};
</script>

<template>
  <nav
    :class="{
      fixed: navPosition === fixed ? 'fixed' : '',
      transparent: bgColor === transparent,
    }"
  >
    <div class="logo">
      <a href="#Home">
        <img src="../assets/img/avada-music-logo.png" alt="" />
      </a>
    </div>

    <div class="nav-menu" v-if="menuBar">
      <i
        class="fa-solid fa-bars nav-bar"
        v-if="displayMenu === false"
        @click="showMenu"
      ></i>
      <i class="fa-solid fa-x nav-bar" v-if="displayMenu" @click="showMenu"></i>

      <ul class="nav-links" v-show="displayMenu">
        <li v-for="link in linksArray">
          <a :href="`#` + link" @click="showMenu">{{ link }}</a>
        </li>
      </ul>
    </div>
    <div class="nav-menu-alt" v-else>
      <ul>
        <li v-for="link in linksArray">
          <a :href="`#` + link" @click="showMenu">{{ link }}</a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<style scoped lang="scss">
@use "../style/partials/variables" as *;
@use "../style/partials/mixin" as *;

nav {
  /* DEBUG */

  background-color: $material-ebony-clay;
  position: relative;

  &.transparent {
    background-color: transparent;
  }

  &.fixed {
    position: fixed;
    top: 0;
    left: 0;
    z-index: 999;
  }

  height: 80px;
  width: 100%;
  @include flex(row, space-between, center);
  padding: 0 2rem;

  .logo {
    width: 150px;
    z-index: 3;
  }

  .nav-menu {
    width: 100px;
    @include flex(row, center, center);
    color: white;
    .nav-bar {
      z-index: 3;
      cursor: pointer;
    }

    .nav-links {
      @include flex(column, center, center);
      gap: 2rem;
      position: absolute;
      width: 100%;
      height: 100vh;
      top: 0px;
      right: 0;
      background-color: $material-mandy;
      z-index: 2;
    }
  }

  .nav-menu-alt {
    width: 50%;
    ul {
      @include flex(row, center, center);
      width: 100%;
      gap: 1rem;
      color: $cube-bombay;
      li {
        &:hover {
          color: $cube-white;
        }
      }
    }
  }
}
</style>
