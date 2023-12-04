<script>
import AppNav from "./AppNav.vue";

export default { components: { AppNav } };
</script>

<template>
  <h2>HEADER</h2>

  <!-- Nav -->
  <AppNav />
  <!-- /Nav -->

  <!-- Hero -->
  <h3>Hero</h3>
  <!-- /Hero -->
</template>

<style scoped lang="scss">
@use "../style/partials/variables" as *;
</style>
