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
  padding: 0.7rem 2rem;
  text-align: center;

  &.primary {
    background-color: $material-mandy;
    transition: all 0.5s;
    border: 1px solid transparent;

    &:hover {
      background-color: transparent;
      border: 1px solid $material-mandy;
    }
  }
  &.secondary {
    background-color: transparent;
    border: 1px solid $cube-white;
    transition: all 0.5s;
    &:hover {
      color: $material-blue-zodiac;
      background-color: $cube-white;
    }
  }
}
</style>
