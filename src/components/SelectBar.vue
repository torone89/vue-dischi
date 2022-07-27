<template>
  <div class="select-box d-flex justify-content-center pt-3">
    <select
      class="form-select w-25"
      @change="genreChanged($event)"
      name="select"
      id=""
    >
      <option value="all">Seleziona il Genere</option>
      <option v-for="(genre, index) in genres" :key="index" :value="genre">
        {{ genre }}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  name: "SelectBar",
  props: {
    genres: Array,
  },
  methods: {
    genreChanged(event) {
      const value = event.target.value;
      this.$emit("genre-changed", value);
    },
  },
};
</script>


<style lang="scss" scoped>
.select-box {
  background-color: #1d2d3b;
}
</style>