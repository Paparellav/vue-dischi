<template>
  <div class="col">
    <div class="item__card text-center mt-5">
      <div class="item__card-img">
        <img :src="cardObj.poster" :alt="cardObj.title" />
      </div>
      <h3 class="text-uppercase fw-bold">{{ cardObj.title }}</h3>
      <div class="album-info">
        <div>{{ cardObj.author }}</div>
        <div>{{ cardObj.year }}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AppCardThumb",
  props: ["cardObj"],
};
</script>

<style lang="scss">
@import "../style/common.scss";
@import "../style/variables.scss";

.item__card {
  width: 190px;
  height: 360px;
  color: $primary-text-color;
  background-color: $primary-bg-color;

  &-img {
    width: 150px;
    width: 150px;
    margin: auto;
    padding: 1.5rem 0;

    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }

  h3 {
    max-width: 170px;
    margin: auto;
    font-size: 1.3rem;
    margin-bottom: 1rem;
  }

  .album-info {
    color: $secondary-text-color;
    font-size: 1.1rem;
  }
}
</style>
