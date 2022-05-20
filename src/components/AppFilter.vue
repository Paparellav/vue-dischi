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
    <div class="filter-bonus">
      <select
        name=""
        id=""
        v-model="checkedValue2"
        @change="$emit('checkArtist', checkedValue2)"
      >
        <option value="">Qualsiasi</option>
        <option value="bon jovi">Bon Jovi</option>
        <option value="queen">Queen</option>
        <option value="sting">Sting</option>
        <option value="steve gadd band">Steve Gadd Band</option>
        <option value="iron maiden">Iron Maiden</option>
        <option value="eric clapton">Eric Clapton</option>
        <option value="deep purple">Deep Purple</option>
        <option value="metallica">Metallica</option>
        <option value="dave weckl">Dave Weckl</option>
        <option value="michael jackson">Michael Jackson</option>
      </select>
    </div>
  </div>
</template>

<script>
export default {
  name: "AppFilter",
  data: function () {
    return {
      checkedValue: "",
      checkedValue2: "",
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

.filter-bonus {
  text-align: center;
  margin-top: 1rem;
  font-size: 1.3rem;

  select {
    width: 250px;
    padding: 0.3rem;
  }
}
</style>
