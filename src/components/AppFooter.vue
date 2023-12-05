<script>
import AppNav from "./AppNav.vue";

export default { components: { AppNav } };
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
</template>

<style scoped lang="scss">
@use "../style/partials/variables" as *;
</style>
