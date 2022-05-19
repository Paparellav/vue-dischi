<template>
  <div class="loading">LOADING...</div>
</template>

<script>
export default {
  name: "AppLoading",
};
</script>

<style lang="scss" scoped>
.loading {
  font-size: 4rem;
  padding: 0.5rem 1rem;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  color: greenyellow;
  background-color: white;
  border-radius: 5px;
}
</style>
