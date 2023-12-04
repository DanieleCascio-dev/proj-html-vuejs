<script>
import MainView from "./MainView.vue";

export default { components: { MainView } };
</script>

<template>
  <!-- Music is life -->
  <section class="life">
    <h2 class="title">Music Is Life</h2>
    <hr class="breakline" />
    <p class="text">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Eius laudantium
      veritatis repellendus est! Asperiores quae cum modi ipsa ex sapiente porro
      nemo beatae minima incidunt
    </p>
  </section>
  <!-- /Music is life -->

  <!-- band news -->
  <section class="band">
    <h2 class="title">Latest Band News</h2>
    <hr class="breakline" />
    <p class="text">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Eius laudantium
      veritatis repellendus est! Asperiores quae cum modi ipsa ex sapiente porro
      nemo beatae minima incidunt
    </p>
    <div>GRIGLIA</div>
  </section>
  <!-- /band news -->

  <!-- view section -->
  <MainView viewText="View all latest news" />

  <!-- view section -->

  <!-- quote section -->
  <div>quote</div>
  <!-- /quote section -->

  <!-- live dates -->
  <div>live dates</div>
  <!-- /live dates -->

  <!-- view section -->
  <div>VIEW</div>
  <!-- view section -->
</template>

<style scoped lang="scss">
@use "../style/partials/variables" as *;
@use "../style/partials/mixin" as *;

.life {
  width: 100%;
  height: 200px;
  background-color: lighten($cube-charade, 5%);
  @include flex(column, center, center);
  gap: 1rem;
}

.band {
  padding: 2rem;
  width: 100%;
  min-height: 800px;
  background-color: $cube-charade;
  @include flex(column, flex-start, center);
  gap: 1rem;
}

.title {
  color: $cube-white;
}

.text {
  text-align: center;
  color: $median-tapa;
  @include container;
}

.breakline {
  width: 15%;
  text-align: center;
  border: 1px solid $cube-mid-gray;
}
</style>
