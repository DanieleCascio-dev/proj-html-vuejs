<script>
export default {
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
  <nav>
    <div class="logo">
      <img src="../assets/img/avada-music-logo.png" alt="" />
    </div>

    <div class="nav-menu">
      <i class="fa-solid fa-bars" @click="showMenu"></i>

      <ul class="nav-links" v-show="displayMenu">
        <li>Link</li>
      </ul>
    </div>
  </nav>
</template>

<style scoped lang="scss">
@use "../style/partials/variables" as *;
@use "../style/partials/mixin" as *;

nav {
  /* DEBUG */
  border: 1px dashed black;
  background-color: darkgray;

  height: 80px;
  width: 100%;
  @include flex(row, space-between, center);
  padding: 0 2rem;

  .logo {
    width: 150px;
  }

  .nav-menu {
    width: 200px;
    @include flex(row, center, center);
    cursor: pointer;

    .nav-links {
      @include flex(row, center, center);
    }
  }
}
</style>
