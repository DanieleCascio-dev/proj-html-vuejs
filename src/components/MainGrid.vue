<script>
import AppCard from "./AppCard.vue";

export default {
  data() {
    return {};
  },
  components: { AppCard },
};
</script>

<template>
  <div class="row">
    <div class="col-left">
      <AppCard
        cardWidth="large"
        cardImg="../src/assets/img/blog_music_techo-400x200.jpg"
        cardtitle="Technology and music"
        cardText="nulla magni aut excepturi quae amet. Incidunt  molestias consequatur!"
      />
    </div>
    <div class="col-right"></div>
  </div>
</template>

<style scoped lang="scss">
@use "../style/partials/variables" as *;
@use "../style/partials/mixin" as *;
.row {
  width: 100%;
  /* debug */
  min-height: 500px;
  border: 1px solid lightblue;
  @include flex(row, center, center);
  .col-left {
    width: 60%;
    min-height: 500px;

    /* debug */
    border: 1px solid lightgreen;
  }

  .col-right {
    width: 40%;
    min-height: 500px;
    /* debug */
    border: 1px solid lightcoral;
  }
}
</style>
