<script>
export default {
  props: {
    cardWidth: String,
    cardImg: String,
    cardtitle: String,
    cardText: String,
  },
};
</script>

<template>
  <div class="card" :class="cardWidth">
    <div class="top-card">
      <img :src="cardImg" alt="" />
    </div>
    <div class="hover-section">
      <h3>
        <a href="">{{ cardtitle }}</a>
      </h3>
    </div>
    <div class="bottom-card">
      <h3>{{ cardtitle }}</h3>
      <p>
        {{ cardText }}
      </p>
    </div>
  </div>
</template>

<style scoped lang="scss">
@use "../style/partials/variables" as *;
@use "../style/partials/mixin" as *;
.card {
  @include flex(column, center, center);
  position: relative;

  &:hover > .hover-section {
    opacity: 100%;
  }
  &:hover > .bottom-card {
    opacity: 0%;
  }
  .hover-section {
    position: absolute;
    width: 100%;
    height: 100%;
    background-color: #eb4b54;
    filter: opacity(50%);
    color: $cube-white;
    @include flex(row, center, center);
    opacity: 0%;
    transition: all 0.3s;
  }
  &.large {
    width: 100%;
  }
  &.mid {
    width: calc(100% / 2);
  }

  .top-card {
    width: 100%;
    height: 200px;

    img {
      width: 100%;
      height: 100%;
    }
  }
  .bottom-card {
    position: absolute;
    bottom: 0;
    right: 0;
    background-color: lighten($cube-charade, 5%);
    padding: 0.5rem 1rem;
    width: 100%;
    opacity: 100%;
    transition: all, 0.3s;
    h3 {
      color: $material-mandy;
      margin-bottom: 0.5rem;
      font-size: 0.8rem;
    }
    p {
      color: $median-tapa;
      font-size: 0.7rem;
    }
  }
}
</style>
