<script>
import AppNav from "./AppNav.vue";

export default {
  components: { AppNav },
  props: {
    leftLinks: Array,
  },
  data() {
    return {
      icons: [
        "fa-brands fa-facebook",
        "fa-brands fa-twitter",
        "fa-brands fa-instagram",
        "fa-brands fa-youtube",
      ],
    };
  },
};
</script>

<template>
  <AppNav
    navPosition=""
    bgColor=""
    :menuBar="false"
    :linksArray="[
      'Home',
      'Meet The Band',
      'Live Dates',
      'Latest News',
      'Albums',
      'Fans',
    ]"
  />
  <section class="bottom">
    <div class="left-links">
      <ul>
        <li v-for="link in leftLinks" :key="link">
          <a href="">{{ link }} </a>
        </li>
      </ul>
    </div>
    <div class="right-links">
      <ul>
        <li v-for="icon in icons" :key="icon">
          <a href=""><i :class="icon"></i></a>
        </li>
      </ul>
    </div>
  </section>
</template>

<style scoped lang="scss">
@use "../style/partials/variables" as *;
@use "../style/partials/mixin" as *;

.bottom {
  height: 60px;
  background-color: $cube-charade;
  @include flex(row, space-between, center);

  .left-links {
    width: 60%;
    @include flex(row, flex-start, center);
    padding-left: 2rem;
    ul {
      @include flex(row, center, center);
      font-size: 0.6rem;
      gap: 1rem;
      color: $cube-bombay;

      li {
        &:nth-child(1)::after,
        &:nth-child(2)::after,
        &:nth-child(3)::after {
          content: "|";
          margin-left: 0.5rem;
        }
      }
    }
  }
  .right-links {
    width: 20%;
    ul {
      @include flex(row, center, center);
      gap: 0.5rem;

      i {
        padding: 0.5rem;
        background-color: $material-ebony-clay;
        color: $cube-bombay;
      }
    }
  }
}
</style>
