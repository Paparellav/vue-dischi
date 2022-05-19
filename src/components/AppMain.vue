<template>
  <section>
    <div v-if="loading" class="container">
      <AppLoading />
    </div>
    <div v-else class="container">
      <div class="row row-cols-5">
        <AppCardThumb
          v-for="(item, index) in cardsArray"
          :key="index"
          :cardObj="item"
        />
      </div>
    </div>
  </section>
</template>

<script>
import AppCardThumb from "./AppCardThumb.vue";
import axios from "axios";
import AppLoading from "./AppLoading.vue";

export default {
  name: "AppMain",
  components: {
    AppCardThumb,
    AppLoading,
  },
  data: function () {
    return {
      cardsArray: [],
      loading: true,
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
};
</script>

<style lang="scss" scoped>
@import "../style/common.scss";
@import "../style/variables.scss";
</style>
