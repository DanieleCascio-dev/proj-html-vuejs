<script>
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import AppFooter from "./components/AppFooter.vue";

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
  <AppFooter
    :leftLinks="[
      '@ Copyright 2012-2020',
      'AVADA THEME BY THEMEFUSION',
      'ALL RIGHTS RESERVED',
      'POWERED BY WORDPRESS',
    ]"
  />
  <!-- /Footer -->
</template>

<style lang="scss">
@use "../src/style/general.scss";
@import "@fortawesome/fontawesome-free/css/all.css";
</style>
