<template>
  <section>
    <div class="container">
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

export default {
  name: "AppMain",
  components: {
    AppCardThumb,
  },
  data: function () {
    return {
      cardsArray: [],
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        this.cardsArray = response.data.response;
      });
  },
};
</script>

<style lang="scss" scoped>
@import "../style/common.scss";
@import "../style/variables.scss";
</style>
