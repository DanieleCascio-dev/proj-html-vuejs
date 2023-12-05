<script>
import AppButton from "./AppButton.vue";

export default {
  data() {
    return {
      displayCard: false,
      datesList: [
        "17/08/2020 GEM FESTIVAL 2020 ANAKALIA, GEORGIA",
        "24/9/2020 GROOVEFEST DOMENICAL REPUBLIC",
        "31/10/2020 OASIS FESTIVAL 2020 MARRAKECH, MOROCCO",
        "07/11/2020 MOGA FESTIVAL - ESSAOURIA, MOROCCO",
        "10/12/2020 ENVISION FESTIVAL - UVITA, COSTA RICA",
      ],
    };
  },
  methods: {
    showCard() {
      this.displayCard = !this.displayCard;
    },
  },
  components: { AppButton },
};
</script>

<template>
  <ul>
    <li v-for="date in datesList" :key="datesList.length">
      <span @click="showCard"><i class="fa-solid fa-plus icon"></i></span>
      <span class="text">{{ date }}</span>
      <div class="card" v-show="displayCard">
        <div class="position">
          <img src="../assets/img/fss-demo-main-400x300.jpg" alt="" />
        </div>
        <div class="info">
          <h3>untold stories</h3>
          <p>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Temporibus
            facilis pariatur ab iste, saepe a voluptates voluptas eaque ullam
            voluptatem illo nihil, doloremque assumenda repudiandae soluta
            eligendi vel magni delectus.
          </p>
          <div class="button">
            <AppButton btnText="Book Now" btnClass="primary" />
          </div>
        </div>
      </div>
    </li>
  </ul>
</template>

<style scoped lang="scss">
@use "../style/partials/variables" as *;
@use "../style/partials/mixin" as *;

li {
  padding: 0.5rem 1rem;
  background-color: $material-ebony-clay;
  margin-bottom: 1rem;
  .icon {
    cursor: pointer;
    color: $cube-white;
    font-size: 0.5rem;
    vertical-align: middle;
  }
  .text {
    margin-left: 1.5rem;
    color: $material-mandy;
    vertical-align: middle;
  }

  .card {
    margin-top: 1rem;
    @include flex(row, center, center);
    gap: 1.5rem;

    .position {
      width: 30%;
    }
    .info {
      width: 70%;
      @include flex(column, center, flex-start);
      gap: 1rem;

      h3 {
        color: $cube-white;
      }
      p {
      }
      .button {
        color: $cube-white;
      }
    }
  }
}
</style>
