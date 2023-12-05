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
      <img src="../assets/img/avada-music-logo.png" alt="" />
    </div>

    <div class="nav-menu" v-if="menuBar">
      <i class="fa-solid fa-bars" @click="showMenu"></i>

      <ul class="nav-links" v-show="displayMenu">
        <li>Link</li>
      </ul>
    </div>
    <div class="nav-menu-alt" v-else>
      <ul>
        <li v-for="link in linksArray">
          <a :href="link">{{ link }}</a>
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
  }

  .nav-menu {
    width: 100px;
    @include flex(row, center, center);
    cursor: pointer;
    color: white;

    .nav-links {
      @include flex(row, center, center);
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
