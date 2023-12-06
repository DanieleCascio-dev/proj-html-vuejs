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
    <div class="col-right">
      <AppCard
        cardWidth="large"
        cardHeght="mid"
        cardImg="../src\assets\img\blog-post1-400x600.jpg"
        cardtitle="it just sounds better"
        cardText="nulla magni aut excepturi quae amet. Incidunt  molestias consequatur!"
      />
      <AppCard
        cardWidth="large"
        cardHeght="mid"
        cardImg="../src\assets\img\blog-post2-400x600.jpg"
        cardtitle="it just sounds better"
        cardText="nulla magni aut excepturi quae amet. Incidunt  molestias consequatur!"
      />
    </div>
  </div>
</template>

<style scoped lang="scss">
@use "../style/partials/variables" as *;
@use "../style/partials/mixin" as *;
.row {
  width: 100%;
  @include flex(row, center, stretch);
  .col-left {
    width: 60%;
  }

  .col-right {
    width: 30%;
    @include flex(column, center, stretch, wrap);
    gap: 2rem;
  }

  .col-left {
    @include flex(row, flex-start, flex-start, wrap);
  }
}
</style>
