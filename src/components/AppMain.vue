<script>
import MainGrid from "./MainGrid.vue";
import MainView from "./MainView.vue";

export default { components: { MainView, MainGrid } };
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
    <div class="grid">
      <MainGrid />
    </div>
  </section>
  <!-- /band news -->

  <!-- view section -->
  <MainView viewText="View all latest news" />

  <!-- view section -->

  <!-- quote section -->
  <section class="quote">
    <div class="top-quote"></div>
    <div class="bottom-quote">
      <p>
        <q>
          <em>
            I just listened to it and said to myself,
            <q>Man, I really love this album.</q> Still, today, it just soounds
            so fresh. It sounds full of ideas. these guys knew what they were
            doing. They're good. And they're inventice. I haven't heard anything
            this year that's as inventive. I don't really expect to.
          </em>
        </q>
      </p>
      <img src="../assets/img/band_interview_play_icon.png" alt="" />
    </div>
  </section>
  <!-- /quote section -->

  <!-- live dates -->
  <section class="live">
    <h2 class="title">Live Dates</h2>
    <hr class="breakline" />
    <p class="text">
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Illo perferendis
      dolorem adipisci eligendi ex sit officia earum sint veniam, nulla suscipit
      at quisquam eveniet provident modi molestias amet porro odio!
    </p>
    <div>COMPONENTE ACCORDION</div>
  </section>
  <!-- /live dates -->

  <!-- view section -->
  <MainView viewText="View all live dates " />
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

  .grid {
    padding: 2rem 0;
    width: 70%;
    margin: 0 auto;
  }
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

/* QUOTE */

.top-quote {
  height: 100px;
  background-image: url(../assets/img/home-testimonial-parallax.jpg);
  background-position: 30% 2%;
  /* background-position-y: top; */
  background-size: cover;
}

.bottom-quote {
  height: 500px;
  background-image: url(../assets/img/home-testimonial-parallax.jpg);
  background-position: 15% 85%;
  background-size: cover;
  gap: 2rem;
  @include flex(column, center, center);
  color: $cube-white;
  text-align: center;
  filter: saturate(80%);

  p {
    @include container;
    line-height: 1.7rem;
    letter-spacing: 2px;
  }

  img {
    width: 80px;
    cursor: pointer;
  }
}

/* LIVE */
.live {
  width: 100%;
  height: 500px;
  padding: 2rem;
  background-color: $cube-charade;
  @include flex(column, flex-start, center);
  gap: 1rem;
}
</style>
