<template>
  <div class="select-box d-flex justify-content-center pt-3">
    <select
      v-model="selected"
      @change="$emit('selectedGenre', selected)"
      class="form-select w-25"
    >
      <option value="">Seleziona il Genere</option>
      <option v-for="(genre, index) in values" :key="index" :value="genre">
        {{ genre }}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  props: {
    values: Array,
  },
  data() {
    return {
      selected: "",
    };
  },
};
</script>


<style lang="scss" scoped>
</style>