<script>
export default {
  props: {
    viewText: String,
  },
};
</script>

<template>
  <div>
    <p>
      <a href="">{{ viewText }}</a>
    </p>
  </div>
</template>

<style scoped lang="scss">
@use "../style/partials/variables" as *;
@use "../style/partials/mixin" as *;

div {
  width: 100%;
  height: 100px;
  background-color: $material-mandy;
  @include flex(row, center, center);
  color: $cube-white;
  line-height: 100px;
  font-weight: 400;
  letter-spacing: 1px;
  transition: all 0.8s;

  &:hover {
    background-color: $cube-white;
    color: $cube-charade;
  }

  a {
    text-decoration: none;
    color: inherit;
    text-transform: uppercase;
  }
}
</style>
