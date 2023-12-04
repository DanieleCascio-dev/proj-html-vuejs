<script>
import AppFooter from "./components/AppFooter.vue";
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";

export default {
  data() {
    return {};
  },
  components: { AppHeader, AppMain, AppFooter },
  methods: {},
};
</script>

<template>
  <!-- Header -->
  <AppHeader />
  <!-- /Header -->

  <!-- Main -->
  <AppMain />
  <!-- /Main -->

  <!-- Footer -->
  <AppFooter />
  <!-- /Footer -->
</template>

<style lang="scss">
@use "../src/style/general.scss";
@import "@fortawesome/fontawesome-free/css/all.css";
</style>
