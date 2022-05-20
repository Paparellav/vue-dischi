<template>
  <section>
    <AppFilter @checkGenre="filterGenre($event)" />
    <div v-if="loading" class="container">
      <AppLoading />
    </div>
    <div v-else class="container">
      <div class="row row-cols-5">
        <AppCardThumb
          v-for="(item, index) in filteredArray"
          :key="index"
          :cardObj="item"
        />
      </div>
    </div>
  </section>
</template>

<script>
import AppCardThumb from "./AppCardThumb.vue";
import AppLoading from "./AppLoading.vue";
import AppFilter from "./AppFilter.vue";
import axios from "axios";

export default {
  name: "AppMain",
  components: {
    AppCardThumb,
    AppLoading,
    AppFilter,
  },
  data: function () {
    return {
      cardsArray: [],
      loading: true,
      genre: "",
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        this.cardsArray = response.data.response;
        this.loading = false;
      });
  },
  methods: {
    filterGenre(event) {
      this.genre = event;
      console.log(this.genre);
    },
  },
  computed: {
    filteredArray() {
      const filteredArray = this.cardsArray.filter((e) => {
        return e.genre.toLowerCase().includes(this.genre);
      });
      return filteredArray;
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../style/common.scss";
@import "../style/variables.scss";
</style>
