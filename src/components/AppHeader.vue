<script>
import AppButton from "./AppButton.vue";
import AppNav from "./AppNav.vue";

export default { components: { AppNav, AppButton } };
</script>

<template>
  <!-- Nav -->
  <AppNav
    :navPosition="fixed"
    :bgColor="transparent"
    :menuBar="true"
    :linksArray="[
      'Home',
      'Meet The Band',
      'Live Dates',
      'Latest News',
      'Albums',
      'Fans',
    ]"
  />
  <!-- /Nav -->

  <!-- Hero -->
  <div class="hero" id="Home">
    <h1>Untold Stories</h1>
    <p><em>There is an untold story behind every favorite song.</em></p>
    <div class="buttons">
      <AppButton btnText="Latest album" btnClass="primary" />
      <AppButton btnText="Live Dates" btnClass="secondary" />
    </div>
  </div>
  <!-- /Hero -->
</template>

<style scoped lang="scss">
@use "../style/partials/variables" as *;
@use "../style/partials/mixin" as *;

.hero {
  height: 500px;

  @include flex(column, center, center);
  gap: 1rem;
  background-image: url(../assets/img/home_slider.jpg);
  background-position: center;
  background-size: cover;

  color: white;

  h1 {
    font-size: 5rem;
  }

  p {
    font-weight: 500;
    letter-spacing: 1px;
    margin-bottom: 1.5rem;
  }

  .buttons {
    @include flex(row, center, center);
    gap: 2rem;
  }
}
</style>
