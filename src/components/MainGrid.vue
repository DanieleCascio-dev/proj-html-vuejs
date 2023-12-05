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
        cardHeght="small"
        cardImg="../src/assets/img/blog_music_techo-400x200.jpg"
        cardtitle="Technology and music"
        cardText="nulla magni aut excepturi quae amet. Incidunt  molestias consequatur!"
      />
      <AppCard
        cardWidth="mid"
        cardHeght="mid"
        cardImg="../src/assets/img/blog-post3-400x600.jpg"
        cardtitle="While my guitar gently weeps"
        cardText="nulla magni aut excepturi quae amet. Incidunt  molestias consequatur!"
      />
      <AppCard
        cardWidth="mid"
        cardHeght="mid"
        cardImg="../src/assets/img/blog-post4-400x600.jpg"
        cardtitle="it just sounds better"
        cardText="nulla magni aut excepturi quae amet. Incidunt  molestias consequatur!"
      />
      <AppCard
        cardWidth="large"
        cardHeght="small"
        cardImg="../src/assets/img/blog_flavor_rock-400x200.jpg"
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
  min-height: 800px;
  border: 1px solid lightblue;
  @include flex(row, center, center);
  .col-left {
    width: 60%;
    min-height: 800px;

    /* debug */
    border: 1px solid lightgreen;
  }

  .col-right {
    width: 40%;
    min-height: 800px;
    /* debug */
    border: 1px solid lightcoral;
  }

  .col-left {
    @include flex(row, flex-start, flex-start, wrap);
  }
}
</style>
