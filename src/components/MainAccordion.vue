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
          position:
            "https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2946.3201924093382!2d41.55194697511633!3d42.39962633260241!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x405dd353aaaaaaab%3A0xc41938c02329eac9!2sGEM%20FEST!5e0!3m2!1sit!2sit!4v1701865157481!5m2!1sit!2sit",
          isOpen: false,
        },
        {
          title: "24/9/2020 GROOVEFEST DOMENICAL REPUBLIC",
          subtitle: "Untold stories",
          text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Temporibus facilis pariatur ab iste, saepe a voluptates voluptas eaque voluptatem illo nihil, doloremque assumenda repudiandae solut eligendi vel magni delectus.",
          position:
            "https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d241952.8189363873!2d-68.63615508795105!3d18.64097105074809!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x8ea891645dcbfe77%3A0x61881cfaed12f6f3!2sPunta%20Cana%2C%20Repubblica%20Dominicana!5e0!3m2!1sit!2sit!4v1701866255239!5m2!1sit!2sit",
          isOpen: false,
        },
        {
          title: "31/10/2020 OASIS FESTIVAL 2020 MARRAKECH, MOROCCO",
          subtitle: "Untold stories",
          text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Temporibus facilis pariatur ab iste, saepe a voluptates voluptas eaque voluptatem illo nihil, doloremque assumenda repudiandae solut eligendi vel magni delectus.",
          position:
            "https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d108702.95891179776!2d-8.090253815924601!3d31.634741149556767!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0xdafee8d96179e51%3A0x5950b6534f87adb8!2sMarrakech%2C%20Marocco!5e0!3m2!1sit!2sit!4v1701866499195!5m2!1sit!2sit",
          isOpen: false,
        },
        {
          title: "07/11/2020 MOGA FESTIVAL - ESSAOURIA, MOROCCO",
          subtitle: "Untold stories",
          text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Temporibus facilis pariatur ab iste, saepe a voluptates voluptas eaque voluptatem illo nihil, doloremque assumenda repudiandae solut eligendi vel magni delectus.",
          position:
            "https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d13611.96126310578!2d-9.771535179913533!3d31.46945256833016!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0xdad9b1c1bcb6f5b%3A0x6bdde9b95ae1252!2sSofitel%20Essaouira%20Mogador%20Golf%20%26%20Spa!5e0!3m2!1sit!2sit!4v1701866037885!5m2!1sit!2sit",
          isOpen: false,
        },
        {
          title: "10/12/2020 ENVISION FESTIVAL - UVITA, COSTA RICA",
          subtitle: "Untold stories",
          text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Temporibus facilis pariatur ab iste, saepe a voluptates voluptas eaque voluptatem illo nihil, doloremque assumenda repudiandae solut eligendi vel magni delectus.",
          position:
            "https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3938.6836685921608!2d-83.7704542242267!3d9.182980286558077!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x8fa159d1ab7ef603%3A0x97fedf8fe56d2356!2sEnvision%20Festival!5e0!3m2!1sit!2sit!4v1701866557399!5m2!1sit!2sit",
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
          <iframe
            :src="date.position"
            width="200"
            height="150"
            style="border: 0"
            allowfullscreen=""
            loading="lazy"
            referrerpolicy="no-referrer-when-downgrade"
          ></iframe>
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
    gap: 2rem;

    .position {
      width: 30%;
    }
    .info {
      margin-left: 1rem;
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
