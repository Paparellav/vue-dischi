<template>
  <header class="header">
    <div class="header__logo">
      <img src="../assets/img/logo-spotify.png" alt="logo-spotify" />
    </div>
  </header>
</template>

<script>
export default {
  name: "AppHeader",
};
</script>

<style lang="scss" scoped>
@import "../style/common.scss";
@import "../style/variables.scss";

.header {
  width: 100%;
  height: 75px;
  display: flex;
  align-items: center;
  color: $primary-text-color;
  background-color: $primary-bg-color;

  &__logo {
    width: 55px;
    padding-left: 0.5rem;
    margin-left: 2rem;
  }
}
</style>
