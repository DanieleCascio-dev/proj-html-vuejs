<script>
export default {
  props: {
    btnText: String,
    btnClass: String,
  },
};
</script>

<template>
  <div v-bind:class="btnClass" class="btn">
    <a href=""> {{ btnText }} </a>
  </div>
</template>

<style scoped lang="scss">
@use "../style/partials/variables" as *;
@use "../style/partials/mixin" as *;

.btn {
  padding: 1rem 2rem;
  &.primary {
    background-color: $material-mandy;
    transition: all 0.5s;

    &:hover {
      background-color: lighten($material-mandy, 5%);
    }
  }
  &.secondary {
    background-color: transparent;
    transition: all 0.5s;
    &:hover {
      color: $material-blue-zodiac;
      background-color: $cube-white;
    }
  }
}
</style>
