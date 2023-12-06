<script>
import AppButton from "./AppButton.vue";

export default {
  data() {
    return {
      datesList: [
        {
          title: "17/08/2020 GEM FESTIVAL 2020 ANAKALIA, GEORGIA",
          subtitle: "Untold stories",
          text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Temporibus facilis pariatur ab iste, saepe a voluptates voluptas eaque voluptatem illo nihil, doloremque assumenda repudiandae solut eligendi vel magni delectus.",
          isOpen: false,
        },
        {
          title: "24/9/2020 GROOVEFEST DOMENICAL REPUBLIC",
          subtitle: "Untold stories",
          text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Temporibus facilis pariatur ab iste, saepe a voluptates voluptas eaque voluptatem illo nihil, doloremque assumenda repudiandae solut eligendi vel magni delectus.",
          isOpen: false,
        },
        {
          title: "31/10/2020 OASIS FESTIVAL 2020 MARRAKECH, MOROCCO",
          subtitle: "Untold stories",
          text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Temporibus facilis pariatur ab iste, saepe a voluptates voluptas eaque voluptatem illo nihil, doloremque assumenda repudiandae solut eligendi vel magni delectus.",
          isOpen: false,
        },
        {
          title: "07/11/2020 MOGA FESTIVAL - ESSAOURIA, MOROCCO",
          subtitle: "Untold stories",
          text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Temporibus facilis pariatur ab iste, saepe a voluptates voluptas eaque voluptatem illo nihil, doloremque assumenda repudiandae solut eligendi vel magni delectus.",
          isOpen: false,
        },
        {
          title: "10/12/2020 ENVISION FESTIVAL - UVITA, COSTA RICA",
          subtitle: "Untold stories",
          text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Temporibus facilis pariatur ab iste, saepe a voluptates voluptas eaque voluptatem illo nihil, doloremque assumenda repudiandae solut eligendi vel magni delectus.",
          isOpen: false,
        },
      ],
    };
  },
  methods: {
    showCard(index) {
      this.datesList[index].isOpen = !this.datesList[index].isOpen;
      // console.log(this.datesList[index].isOpen);
    },
  },
  components: { AppButton },
};
</script>

<template>
  <ul>
    <li
      v-for="(date, index) in datesList"
      :key="datesList.length"
      @mouseleave="date.isOpen = false"
    >
      <span @click="showCard(index)"
        ><i class="fa-solid fa-plus icon" v-show="date.isOpen === false"></i>
        <i class="fa-solid fa-minus icon minus" v-show="date.isOpen"></i
      ></span>
      <span @click="showCard(index)" class="text">{{ date.title }}</span>
      <div class="card" v-if="date.isOpen">
        <div class="position">
          <img src="../assets/img/fss-demo-main-400x300.jpg" alt="" />
        </div>
        <div class="info">
          <h3>{{ date.subtitle }}</h3>
          <p>
            {{ date.text }}
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
  &:hover {
    background-color: lighten($material-ebony-clay, 5%);
  }
  .icon {
    cursor: pointer;
    color: $cube-white;
    font-size: 0.5rem;
    padding: 0.2rem;
    vertical-align: middle;
    &:hover {
      background-color: $material-mandy;
    }
  }

  .minus {
    background-color: $material-mandy;
    color: $cube-white;
  }
  .text {
    cursor: pointer;
    margin-left: 1.5rem;
    color: $material-mandy;
    vertical-align: middle;
  }

  .card {
    margin-top: 1rem;
    margin-bottom: 2rem;
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
        color: $median-tapa;
      }
      .button {
        color: $cube-white;
      }
    }
  }
}
</style>
