<script>
import AppNav from "./AppNav.vue";

export default { components: { AppNav } };
</script>

<template>
  <!-- Nav -->
  <AppNav :navPosition="fixed" />
  <!-- /Nav -->

  <!-- Hero -->
  <div class="hero">
    <h1>Untold Stories</h1>
    <h3>There is an untold story behind every favorite song</h3>
  </div>
  <!-- /Hero -->
</template>

<style scoped lang="scss">
@use "../style/partials/variables" as *;
@use "../style/partials/mixin" as *;

.hero {
  /* debug */
  min-height: 500px;
  border: 1px solid darkcyan;

  @include flex(column, center, center);
  gap: 1rem;
  background-image: url(../assets/img/home_slider.jpg);
  background-position: center;
  background-size: cover;

  color: white;
}
</style>
