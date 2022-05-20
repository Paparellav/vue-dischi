<template>
  <div class="filter">
    <select
      name=""
      id=""
      v-model="checkedValue"
      @change="$emit('checkGenre', checkedValue)"
    >
      <option value="">Qualsiasi</option>
      <option value="rock">Rock</option>
      <option value="pop">Pop</option>
      <option value="jazz">Jazz</option>
      <option value="metal">Metal</option>
    </select>
  </div>
</template>

<script>
export default {
  name: "AppFilter",
  props: ["cardObj"],
  data: function () {
    return {
      checkedValue: "",
    };
  },
};
</script>

<style lang="scss" scoped>
.filter {
  text-align: center;
  margin-top: 3rem;
  font-size: 1.3rem;

  select {
    width: 250px;
    padding: 0.3rem;
  }
}
</style>
