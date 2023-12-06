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
    <a
      :target="btnText === 'Latest album' ? '_blank' : ''"
      :href="
        btnText === 'Latest album'
          ? 'https://www.google.com/search?q=latest+album+releases&oq=latest+album&gs_lcrp=EgZjaHJvbWUqBwgAEAAYgAQyBwgAEAAYgAQyBggBEEUYOTIICAIQABgWGB4yCAgDEAAYFhgeMggIBBAAGBYYHjIICAUQABgWGB4yCAgGEAAYFhgeMgYIBxBFGDzSAQg2NDA3ajBqN6gCALACAA&'
          : `#` + btnText
      "
    >
      {{ btnText }}
    </a>
  </div>
</template>

<style scoped lang="scss">
@use "../style/partials/variables" as *;
@use "../style/partials/mixin" as *;

.btn {
  padding: 0.2rem 1.2rem;
  text-align: center;
  a {
    text-transform: uppercase;
    font-size: 0.6rem;
  }
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
